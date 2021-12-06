#  File Structure

ansible
│   ├── hosts
│   ├── microk8s
│   │   ├── tasks
│   │   │   ├── addons.yml
│   │   │   ├── install.yml
│   │   │   └── main.yml
│   │   └── vars
│   │       └── main.yml
│   ├── microk8s.yml
│   ├── ssl
│   │   ├── issuer.yml
│   │   ├── tasks
│   │   │   ├── cert-manager.yml
│   │   │   ├── copy.yml
│   │   │   └── main.yml
│   │   └── values.yml
│   └── ssl.yml
├── LICENSE
└── README.md

# How to Run this monstrosity and open up oblivian 

 Client can be anything (I really prefer Linux [either arch or gentoo] as long as it's got ansible  and ansible-playbook installed. Installing ansible, well there are many different OS's and ways to install it. I installed it via the command line but what should be a universal way (in software there is no such thing, there is just hackish attempts) is to install it with pip (assuming pip is installed).

    python -m pip install --user ansible

You're also going to need git.

https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

The link below, should also help if need me.

https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html


# Clone the repo.

    git clone git@github.com:silverraindog/k8s.git

Now open up these files

| DIR     				  |	File    |  Tochange   |
| :---------------------- | -------:| :---------: |
| ansible 				  | host 	| Hostname_change|
| ansible/microk8s/tasks/ | install.yml |  Username_change|
| ansible/microk8s/tasks/ | install.yml |  Wordpress_password|
| ansible/microk8s/tasks/ | install.yml |  DB_root_password |
| ansible/microk8s/tasks/ | install.yml |  Domain_name   |
| ansible/ssl/tasks/	  | issuer.yml  |  Email_change  |

# NB
looking at some posts when I ran in to an issue, it seems ansible has an issue with IP's. You're more than welcome to use an IP and I did for the majority of testing


# Notes

I know there are better ways to do some of this in ansible, for instance, the passwords, can be encrypted in a vault,etc. This will happen some day (I do plan on using this for personal use)

# Network Diagram

I have tried to put this in to the Readme but I am unable to get it to work. The picture is in the repo.



# Sources used.

https://github.com/istvano/ansible_role_microk8s
https://bitnami.com/stack/wordpress/helm
https://github.com/bitnami/charts/tree/master/bitnami/wordpress/
https://github.com/JessicaGreben/example-nodejs/tree/master/deploy/cert-manager-setup

