Prometheus-Alertmanager to Microsoft Teams Integration

This project demonstrates how to set up Prometheus and Alertmanager with Docker to monitor system metrics and send alerts to a Microsoft Teams channel using Power Automate.

Table of Contents

Overview
Prerequisites
Project Structure
Setup Instructions
1. Configure Prometheus
2. Configure Alertmanager
3. Docker Compose Setup
4. Run the Services
Testing Alerts
Customization
Contributing

Overview

This setup uses Prometheus to scrape system metrics and trigger alerts when specific conditions are met. Alertmanager processes these alerts and sends notifications to Microsoft Teams via a Power Automate webhook. We’ll use Docker Compose to easily run both Prometheus and Alertmanager as containers.

Prerequisites

Before getting started, ensure you have the following:

Docker
Docker Compose
A Microsoft Teams account and a created Power Automate flow with a webhook for receiving alerts.
Project Structure
refer to 'flow.txt' file

Setup Instructions

1. Configure Prometheus
Prometheus is configured to scrape system metrics and send alerts to Alertmanager. The configuration is in the prometheus/prometheus.yml file.

The alerting rules, such as alerts for high CPU usage, are defined in prometheus/alerts.rules.yml.

2. Configure Alertmanager
Alertmanager is responsible for receiving alerts from Prometheus and routing them to Microsoft Teams. The configuration can be found in the alertmanager/alertmanager.yml file.

Make sure to replace the Power Automate webhook URL in the file.

3. Docker Compose Setup
Docker Compose is used to manage both Prometheus and Alertmanager services. The configuration is in docker-compose.yml.

4. Run the Services
Once the configurations are set, run the following command to start the services:


docker-compose up
Prometheus: http://localhost:9090
Alertmanager: http://localhost:9093

Testing Alerts

Simulate High CPU Usage: Use node exporter to simulate high CPU usage.
Check Prometheus: Go to Prometheus UI and check if the alert is firing under the "Alerts" tab.
Check Microsoft Teams: Verify that the alert is sent to Microsoft Teams via the Power Automate webhook.
Customization

You can modify the alert rules in alerts.rules.yml to monitor different metrics like memory, disk I/O, or network latency.

Contributing

Feel free to open a pull request or submit an issue for any bugs or feature requests.
