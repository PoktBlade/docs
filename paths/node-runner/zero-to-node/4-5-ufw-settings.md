# 4-5: Enable UFW

We're almost done, but before we finish we'll make our server more secure by setting firewall rules to limit network exposure. The [Uncomplicated Firewall](https://wiki.ubuntu.com/UncomplicatedFirewall) (UFW) is a security tool that makes configuring the firewall reasonably simple. We'll use it to disable unnecessary ports.

## Ports you need to open

For running a Pocket node, you'll need to open the following ports:

- `22`: SSH
- `80`: HTTP
- `443`: HTTPS
- `8081`: For the Pocket HTTP API
- `26656`: For the Pocket RPC API

## Use UFW to disable unnecessary ports

To use UFW to configure the firewall:

1. Enable UFW:
    ```bash
    sudo ufw enable
    ```
    {% hint style="info" %}
    Type `y` to confirm.
    {% endhint %}

2. Set the default to deny all incoming connections:
    ```bash
    sudo ufw default deny
    ```

3. Allow the SSH port:
    ```bash
    sudo ufw allow ssh
    ```

4. Allow port 80:
    ```bash
    sudo ufw allow 80
    ```

5. Allow port 443:
    ```bash
    sudo ufw allow 443
    ```

6. Allow port 8081:
    ```bash
    sudo ufw allow 8081
    ```

7. Allow port 26656:
    ```bash
    sudo ufw allow 26656
    ```

That's it for the UFW setup. Let's just check the status to confirm the ports are open. To do that, run the following command:

```bash
sudo ufw status
```

After confirming only the necessary ports are open, you can move on to the next step.