- hosts: localhost
  connection: local
  gather_facts: False
  tasks:
    - name: Create EC2 Keypair
      ec2_key:
        name: mykeypairansible
      no_log: true
      register: key_out
 
 
    - name: Show task output
      debug:
        var: key_out
    - name: Save the key
      copy:
        content: "{{key_out.key.private_key}}"
        dest: mykeypairansible.pem
      when: key_out.changed == True
