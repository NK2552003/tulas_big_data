# Grafana Installation

1. Install the prerequisite packages:

```jsx
sudo apt-get install -y apt-transport-https software-properties-common wget
```

1. Import the GPG key:

```jsx
sudo mkdir -p /etc/apt/keyrings/
wget -q -O - https://apt.grafana.com/gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/grafana.gpg > /dev/null
```

1. To add a repository for stable releases, run the following command:

```jsx
echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```

1. To add a repository for beta releases, run the following command:

```jsx
echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com beta main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```

1. Run the following command to update the list of available packages:

```jsx
sudo apt-get update
```

1. To install Grafana OSS, run the following command:

```jsx
sudo apt-get install grafana
```

1. Start Grafana Service

```jsx
sudo systemctl start grafana-server
sudo systemctl enable grafana-server
```

1. Check if running

```jsx
sudo systemctl status grafana-server
```

1. See the UI

```jsx
http://localhost:3000
```

Default creds:

username: **admin**

password: **admin**

1. Stop Grafana (If you want)

```jsx
sudo systemctl stop grafana-server
```