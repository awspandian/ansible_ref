# ansible_ref



https://docs.ansible.com/ansible/latest/user_guide/modules.html

https://docs.ansible.com/ansible/latest/network/getting_started/basic_concepts.html

https://www.ansible.com/blog/getting-started-writing-your-first-playbook

https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html


strategy - liner
strategy - free
strategy - Batch
serial: <number>

ignore_errors: yes

- command: cat /var/log/server.log
  register: command_output
  failed_when: " 'ERROR' in command_output.stdout"
  
	String Manipulation -Filters
	
  Substitule = The name is {{ my_name }} => The name is Demo
  Upper = The name is {{ my_name | upper }} => The name is DEMO
  Lower = The name is {{ my_name | lower }} => The name is demo
  Title = The name is {{ my_name | title }} => The name is Demo
  Replace = The name is {{ my_name | replace ("Demo","pandian" }} => The name is pandian
  Default = The name is {{ first_name | default("Raja")}}{{"my_name" }} => The name is Raja Pandian 
  
  FILTERS - List and Set
  
  {{ [1,2,3] | min }}     					=> 1
  {{ [1,2,3] | max }}     					=> 3
  {{ [1,2,3] | unique}}   					=> 1,2,3
  {{ [1,2,3] | union([4,5]) }}     			=> 1,2,3,4,5
  {{ [1,2,3] | intersect ([4,5]) }}			=> 4
  {{ 100 | random }}						=> Random Number
  {{ ["This","is","sample"] | join ("") }} 	=> This is sample
  
  FILTERS -File
  
  {{ "/etc/hosts" | basename }}
  {{"c:\windows\hosts" | win_baseame }}
