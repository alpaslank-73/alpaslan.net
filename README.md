This collection provides only one filter and a sample usage is below:

- name: IP List Test
  hosts: localhost
  gather_facts: no
  vars:
    my_prefix: 10.10.10.0/24
  tasks:
    - name: Setting a fact for my list of IP addresses
      set_fact:
        my_ip_addresses: "{{ my_prefix | alpaslan.net.ip_list }}"

    - name: Print list of IP addresses
      debug:
        msg: "{{ my_ip_addresses[1:-1]}}"
