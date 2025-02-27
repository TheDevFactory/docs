# Matrix Bridge Configuration

**Important**: This is only necessary if you made the manual installation, otherwise this is already done by the [setup script](matrix-homeserver-setup.md#automated-installation-recommended).

To access this setting, go to: _**Administration** > **Workspace** > **Settings** > **Federation > Matrix Bridge.**_

![Matrix Bridge Configuration](../../../../../../../.gitbook/assets/2022-07-22\_12-28-56.png)

The following is a brief explanation of each Matrix Bridge configuration option:

* **AppService ID** _(_`Federation_Matrix_id`, _automatically generated by Rocket.Chat)**:**_ A unique identifier for the Application Service.
* **Homeserver Token** _(_`Federation_Matrix_hs_token`, _automatically generated by Rocket.Chat)_**:** A unique homeserver token to authenticate requests to Application Services. Example: _http://localhost:8008_
* **App Service Token** _(_`Federation_Matrix_as_token`, _automatically generated by Rocket.Chat)_**:** A unique Application Service token to authenticate requests to homeservers.
* **Homeserver URL** (`Federation_Matrix_homeserver_url):`The URL of the Matrix server you want to use as your Proxy homeserver.
* **Homeserver Domain** `(Federation_Matrix_homeserver_domain)`**:**  This is your Matrix homeserver's name, the same as you've configured in your Matrix configuration file.
* **Bridge URL** (`Federation_Matrix_bridge_url)`**:** The URL for the Matrix bridge. It is the location you want your bridge should run.

{% hint style="warning" %}
* Make sure the port that you are using for the bridge is free in your host.
* We recommend a brand new Matrix homeserver to be used as your Proxy homeserver.
* We strongly recommend not connecting to this Matrix homeserver using other Matrix clients, if you want to do that, please configure another Matrix homeserver instance.
{% endhint %}

* **AppService User Localpart** (`Federation_Matrix_bridge_localpart`)**:** The bot user associated with the application service (Sometimes it's being used to execute some actions).
* **Registration** (`Federation_Matrix_registration_file`):  Automatically generated and updated by Rocket.Chat based on all the values provided in the above settings (This file is used [to configure the Application Service](matrix-homeserver-setup.md#manual-installation)).
* Click **Save Changes**.
* Paste the registration file in your Application Service into your Matrix homeserver [to enable the bridging process](https://matrix-org.github.io/synapse/latest/application\_services.html) **OR**  create a folder (`app/matrix-federation-config`) inside the build version of Rocket.Chat and create a file `registration.yaml` using the registration file you got from the Rocket.Chat admin panel.
* Restart Matrix homeserver.
* Restart Rocket.Chat.
