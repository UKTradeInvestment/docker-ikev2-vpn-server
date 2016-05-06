# IKEv2 VPN Server on Docker

Recipe to build [`gaomd/ikev2-vpn-server`](https://registry.hub.docker.com/u/gaomd/ikev2-vpn-server/) Docker image.

## Usage

### 1. Start the IKEv2 VPN Server

    docker run -d --name ikev2-vpn-server --restart=always --privileged -e "HOST=vpn.example.com" -p 500:500/udp -p 4500:4500/udp gaomd/ikev2-vpn-server:0.3.0

    you'll find your secred and .mobileconfig in /var/ipsec/*

    make sure you pass correct value for HOST variable

### 2. Install the .mobileconfig (for iOS / OS X)

- **iOS 9 or later**: AirDrop the `.mobileconfig` file to your iOS 9 device, finish the **Install Profile** screen;

- **OS X 10.11 El Capitan or later**: Double click the `.mobileconfig` file to start the *profile installation* wizard.

## Technical Details

Upon container creation, a *shared secret* was generated for authentication purpose, no *certificate*, *username*, or *password* was ever used, simple life!

## License

Copyright (c) 2016 Mengdi Gao, This software is licensed under the [MIT License](LICENSE).

---

\* IKEv2 protocol requires iOS 8 or later, Mac OS X 10.11 El Capitan is supported as well.

\* Install for **iOS 8 or later** or when your AirDrop fails: Send an E-mail to your iOS device with the `.mobileconfig` file as attachment, then tap the attachment to bring up and finish the **Install Profile** screen.
