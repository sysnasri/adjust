# adjust challange for DevOps opportunity 
   The challange consist of a small ansible role that creates fstab entires based on a yaml file. 

     # Part 1: Requirements

          Molecule uses docker as provisioner so please install docker ce in advanced then:
            you can install all packages and dependenices easily via pip3 in the root directory issue the following commands:

                git clone https://github.com/sysnasri/adjust
                pip3 install -r requirements.txt         


          

     # Part 2: Converge test

          - You can test the role before applying it into production servers and see the result, to issue tests run :
            molecule converge
            molecule destroy 



     # Part 3: How to use it?  Create a yaml file and add/change the following contents:
               you can also find main.yaml.example in the root directory.  

              - name: Setup fstab file
                hosts: linux_servers
                gather_facts: yes
                become: yes
                tasks:
                  - name: "Include Fstab Generation file"
                    include_role:
                        name: "adjust"
                    tags:
                        - fstab_generate

     # Part 4: Run the ansible role.

        ansible-playbook -i inventory/cluster1/inventory.yaml main.yaml.example






