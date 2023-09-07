# Network Configuration

`network-config-playbook.yaml` configures the Edgerouter 4.


## First Run

1. Reset the Edgerouter 4 using the reset pin. Hold for about 10 seconds.

2. Plug ethernet cable from computer into `eth0`.

3. Configure wired connection with the a static connection:

    ```
    Gateway:    192.168.1.1
    Subnet:     255.255.255.0
    IP:         192.168.1.10
    ```

    _** replace the IP address with your preferred IP_

4. Run the playbook:

    ```
    ansible-playbook router-config-playbook.yaml --ask-pass -i inventory.yaml -e public_key_path=$PUBLIC_KEY_PATH -e private_key_path=$PRIVATE_KEY_PATH
    ```

    The playbook will prompt for the password for the `ubnt` user. The default password is also `ubnt`.

5. On subsequent runs:

    ```
    ansible-playbook router-config-playbook.yaml -i inventory.yaml -e public_key_path=$PUBLIC_KEY_PATH -e private_key_path=$PRIVATE_KEY_PATH
    ```