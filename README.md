# Code_Kaizen Portainer Collection

This repository contains the `code_kaizen.portainer` Ansible Collection.

## TODO

- [ ] Create stack modules
  - `stack`
    - `state` (enum)
      - `fetched`
        - LIST
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackList
      - `absent`
        - LIST
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackList
          - Look for stack by unique identifier: name
        - DELETE
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackDelete
      - `started`
        - LIST
          - Look for stack by unique identifier: name
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackList
        - POST
          - If the stack does not exist yet, create it
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateKubernetesGit
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateKubernetesFile
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateKubernetesUrl
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateDockerStandaloneFile
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateDockerStandaloneRepository
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateDockerStandaloneString
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateDockerSwarmFile
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateDockerSwarmRepository
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateDockerSwarmString
        - PUT
          - If the stack already exists, update it
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackUpdate
          - If `git`, may also need to call this method
            - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackUpdateGit
        - START
          - Make sure the stack is started
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackStart
      - `stopped`
        - LIST
          - Look for stack by unique identifier: name
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackList
        - POST
          - If the stack does not exist yet, create it
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateKubernetesGit
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateKubernetesFile
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateKubernetesUrl
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateDockerStandaloneFile
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateDockerStandaloneRepository
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateDockerStandaloneString
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateDockerSwarmFile
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateDockerSwarmRepository
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackCreateDockerSwarmString
        - PUT
          - If the stack already exists, update it
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackUpdate
          - If `git`, may also need to call this method
            - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackUpdateGit
        - STOP
          - Make sure the stack is stopped
          - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackStop
    - `associate` (bool)
      - After any other changes driven by the `state` param, re-associate the stack with the endpoint passed as arg
      - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackAssociate
      - Basically, give us permission to reassociate the orphaned stack with the endpoint passed as arg
    - `redeploy` (bool)
      - After any other changes driven by the `state` param, redeploy the stack
      - If `webhook`, use this strategy
        - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/WebhookInvoke
      - If `git`, use this strategy
        - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackGitRedeploy
    - `get_stack_file` (bool)
      - For each stack data returned, add the stack file to the data as an additional attribute
      - https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.5#/stacks/StackFileInspect
- [ ] Create endpoint modules

<!--start requires_ansible-->
<!--end requires_ansible-->

## External requirements

Some modules and plugins require external libraries. Please check the requirements for each plugin or module you use in the documentation to find out which requirements are needed.

## Included content

Please check the included content on the [Ansible Galaxy page for this collection](https://galaxy.ansible.com/code_kaizen/portainer).

<!--start collection content-->
<!--end collection content-->

## Using this collection

```
    ansible-galaxy collection install code_kaizen.portainer
```

You can also include it in a `requirements.yml` file and install it via `ansible-galaxy collection install -r requirements.yml` using the format:

```yaml
collections:
  - name: code_kaizen.portainer
```

To upgrade the collection to the latest available version, run the following command:

```bash
ansible-galaxy collection install code_kaizen.portainer --upgrade
```

You can also install a specific version of the collection, for example, if you need to downgrade when something is broken in the latest version (please report an issue in this repository). Use the following syntax where `X.Y.Z` can be any [available version](https://galaxy.ansible.com/code_kaizen/portainer):

```bash
ansible-galaxy collection install code_kaizen.portainer:==X.Y.Z
```

See [Ansible Using collections](https://docs.ansible.com/ansible/latest/user_guide/collections_using.html) for more details.

## Contributing

### Running Tests

Run all tox integration tests:

```sh
python -m tox --ansible --conf tox-ansible.ini
```

Run tox integration tests for a specific environment:

```sh
python -m tox --conf tox-ansible.ini --ansible -e sanity-py3.12-devel
```

Run tox integration tests for a specific scenario:

```sh
# Unit
python -m tox --conf tox-ansible.ini --ansible --matrix-scope unit
# Integration
python -m tox --conf tox-ansible.ini --ansible --matrix-scope integration
```

Run tox integration tests for a specific environment and a specific scenario:

```sh
# Unit
python -m tox --conf tox-ansible.ini --ansible -e sanity-py3.12-devel --matrix-scope unit
# Integratino
python -m tox --conf tox-ansible.ini --ansible -e sanity-py3.12-devel --matrix-scope integration
```


## Release notes

See the [changelog](https://github.com/codekaizen-github/portainer-ansible-collection/tree/main/CHANGELOG.rst).

## Roadmap

<!-- Optional. Include the roadmap for this collection, and the proposed release/versioning strategy so users can anticipate the upgrade/update cycle. -->

## More information

<!-- List out where the user can find additional information, such as working group meeting times, slack/IRC channels, or documentation for the product this collection automates. At a minimum, link to: -->

- [Ansible Collection overview](https://github.com/ansible-collections/overview)
- [Ansible User guide](https://docs.ansible.com/ansible/devel/user_guide/index.html)
- [Ansible Developer guide](https://docs.ansible.com/ansible/devel/dev_guide/index.html)
- [Ansible Collections Checklist](https://github.com/ansible-collections/overview/blob/main/collection_requirements.rst)
- [Ansible Community code of conduct](https://docs.ansible.com/ansible/devel/community/code_of_conduct.html)
- [The Bullhorn (the Ansible Contributor newsletter)](https://us19.campaign-archive.com/home/?u=56d874e027110e35dea0e03c1&id=d6635f5420)
- [News for Maintainers](https://github.com/ansible-collections/news-for-maintainers)

## Licensing

GNU General Public License v3.0 or later.

See [LICENSE](https://www.gnu.org/licenses/gpl-3.0.txt) to see the full text.
