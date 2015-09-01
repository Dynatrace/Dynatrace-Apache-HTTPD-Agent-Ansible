# Dynatrace-Apache-HTTPServer-Agent-Ansible

An [Ansible](http://www.ansible.com) role for automated deployments of the [Dynatrace](http://www.bit.ly/dttrial) Agent for the Apache HTTP Server.

This role makes the Agent available to the Apache HTTP Server by injecting a *LoadModule* directive into the HTTP Server's config file. **You will have to restart the Apache HTTP Server after placing the agent.**

## Download

The role is available via:

- [Ansible Galaxy](https://galaxy.ansible.com/list#/roles/2681)
- [GitHub](https://github.com/Dynatrace/Dynatrace-Apache-HTTPServer-Agent-Ansible)

## Dependencies

This roles depends on the following roles:

- [Dynatrace-WebServer-Agent](https://galaxy.ansible.com/list#/roles/2625)

## Role Variables

As defined in ```defaults/main.yml```:

| Name                                                    | Default                                  | Description |
|---------------------------------------------------------|------------------------------------------|-------------|
| *dynatrace_apache_agent_linux_agent_path*               | /opt/dynatrace/agent/lib64/libdtagent.so | The path to the Agent library. |
| *dynatrace_apache_agent_linux_apache_config_path*       | /etc/apache2/apache2.conf                | The path to the Apache HTTP Server's config file. |
| *dynatrace_apache_agent_name*                           | apache-dtwsagent                         | The name the Web Server Agent as it appears in Dynatrace. |
| *dynatrace_apache_agent_state*                          | present                                  | Whether the Agent shall be ```present``` or ```absent```. |

dynatrace_apache_agent_name

## Example Playbook

	- hosts: all
	  roles:
	    - role: dynatrace.Dynatrace-Apache-HTTPServer-Agent

## Testing

We use [Test Kitchen](http://kitchen.ci) to automatically test our automated deployments with [Serverspec](http://serverspec.org):

1) Install Kitchen and its dependencies from within the project's directory:

```
gem install bundler
bundle install
```

2) Run tests

```
kitchen test
```

## Additional Resources

- [Blog: How to Automate Enterprise Application Monitoring with Ansible](http://apmblog.dynatrace.com/2015/03/04/how-to-automate-enterprise-application-monitoring-with-ansible/)
- [Blog: How to Automate Enterprise Application Monitoring with Ansible - Part II](http://apmblog.dynatrace.com/2015/04/23/how-to-automate-enterprise-application-monitoring-with-ansible-part-ii/)
- [Slide Deck: Automated Deployments](http://slideshare.net/MartinEtmajer/automated-deployments-slide-share)
- [Slide Deck: Automated Deployments (of Dynatrace) with Ansible](http://www.slideshare.net/MartinEtmajer/automated-deployments-with-ansible)
- [Slide Deck: Testing Ansible Roles with Test Kitchen, Serverspec and RSpec](http://www.slideshare.net/MartinEtmajer/testing-ansible-roles-with-test-kitchen-serverspec-and-rspec-48185017)
- [Tutorials: Automated Deployments (of Dynatrace) with Ansible](https://community.compuwareapm.com/community/display/COE/Tutorials+on+Automated+Deployments#TutorialsonAutomatedDeployments-ansible)

## Questions?

Feel free to post your questions on the Dynatrace Community's [Continuous Delivery Forum](https://community.dynatrace.com/community/pages/viewpage.action?pageId=46628921).

## License

Licensed under the MIT License. See the LICENSE file for details.
[![analytics](https://www.google-analytics.com/collect?v=1&t=pageview&_s=1&dl=https%3A%2F%2Fgithub.com%2FdynaTrace&dp=%2FDynatrace-Apache-HTTPServer-Agent-Ansible&dt=Dynatrace-Apache-HTTPServer-Agent-Ansible&_u=Dynatrace~&cid=github.com%2FdynaTrace&tid=UA-54510554-5&aip=1)]()