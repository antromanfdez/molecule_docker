# Molecule Example for Ansible using docker and systemctl3.py to simulate systemd

This directory contains an example Molecule configuration for an Ansible playbook that allows easy development and testing of the playbook.

The Molecule configuration can be run locally or in a Continuous Integration (CI) environment, to ensure the playbook is always working correctly.

To run the Molecule environment, you must have `molecule` (with it's `docker` driver) and the `docker` Python library installed:
To install pyhton on a virtual environment:

1. Create virtual environment for python
    
    ```
    python3 -m venv molecule-venv
    ```   
    
2. Install the requirements package on a virtual environment. 
        
        pip3 install requirements.txt 
        

        
Once everything is ready, run:
        
    molecule test
        
Or, if you just want to build an environment, have the playbook run inside it, then be able to log in and observe the environment, run:
        
    molecule converge
        
And then, to log into the environment:
        
    molecule login
        
3. Possible error:
    
    Problems:
    
    ```bash
    ....
    ERROR! couldn't resolve module/action 'community.docker.docker_container'. This often indicates a misspelling, missing collection, or incorrect module path.
    
    The error appears to be in '/home/casa/test_molecule2/molecule-venv/lib/python3.9/site-packages/molecule_docker/playbooks/destroy.yml': line 8, column 7, but may
    be elsewhere in the file depending on the exact syntax problem.
    
    The offending line appears to be:
    
      tasks:
        - name: Destroy molecule instance(s)
          ^ here
    ....
    
    ```
    
     Solution: 
    
    ```bash
    ansible-galaxy collection install community.docker
    ```
    



Once everything is ready, run:
    
     molecule test
    
Or, if you just want to build an environment, have the playbook run inside it, then be able to log in and observe the environment, run:
            
    molecule converge
    
And then, to log into the environment:
        
    molecule login
    
## Using code from

 [geerlingguy - ansible-for-devops](https://github.com/geerlingguy/ansible-for-devops/tree/master/molecule)
 

[gdraheim - docker-systemctl](https://github.com/gdraheim/docker-systemctl-replacement)

