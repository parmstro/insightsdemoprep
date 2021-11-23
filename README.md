README.md
# Red Hat Insights Demo Prep
## Experience Insights. Seeing is believing. 

This repo contains the plays that are needed to set up clients for a Red Hat Insights Demo. The plays can:
- Build content views containing old content on Satellite. 
- Deploy systems from those content views
- Run break scripts that disable known features for Insights to find and rememdiate
- Create conditions that will violate certain OpenSCAP scan conditions

A fully functional Satellite 6.9 infrastructure is assumed! This is not for the demo, but for deploying the demo... 
Each demo environment is different, each customer has unique requirements and intrests. Fork the repo and use it to make a demo environment that meets *your* customer's needs.

## Contents

### contentviews
This folder contains the content view definitions to generate the necessary views for RHEL 8 and RHEL 7 systems
The views are based on RHEL 7.9 and RHEL 8.4 from July 2021
Your mileage may vary and you may have to adjust the definitions to meet your current needs.
The plays use cvcreator and cvpromoter from the satellite repository on my github

### deploy
This folder contains the configuration for the host groups and the deployment of systems for the demo
The configurations and code will work with Satellite 6.9, but the details are necessarily unique to my environment. You will have to modify the values to make the configuration suitable for your environment. Items like Compute Resources, Domains, Realms, etc.. are deemed to exist for the Host Group configuration scripts. Yours may be different or may not exist. Configure accordingly.
The plays make use of the hostgroup role and CreateHostFromHostGroup play in the satellite repository on my github
The hostgroup configurations make sure that the system is not automatically registered to Insights. We want to break it first.

### break
This folder contains the plays that will break your systems. Please review the code and test your environment before demoing.

### register
This folder contains the plays that control the registration of your deployed test systems.
There are plays that can be configured to unregister your systems from your satellite and reattach them to the portal or leave them unregistered so that you can show registrations.
There are plays that you can run from the commandline that will make registration easy and painless as part of your demo so you can make things move quickly and smoothly.
Re-register to the satellite or register to the portal.
There are plays that simply register the new systems to Insights...
This way you can demonstrate:
Systems using Insights without Satellite
Systems using Insights with Smart Management
Systems using Insights with Smart Management and Satellite
Systems using Insights, Satellite and Ansible Automation Platform

Enjoy.

If you find a bug or create something you want to share, pull requests are welcome!
