#prometheus setup

This is a sample Prometheus with cAdvisor and Grafana setup to monitor conatiners on AWS, using ec2_discovery

# Pre-requisites

```bash
Sample wordpress app is built, source code present on https://github.com/surenbika/cake.git
```

# To deploy prometheus, cadvisor and grafana stack

```bash
$ docker-compose up -d #to run in daemonizing mode

The Grafana Dashboard is now accessible via: http://<Host IP Address>:3000 for example http://192.168.10.1:3000
username - admin password - foobar (Password is stored in the config.monitoring env file)
```

Post Installation Configuration
```bash
Now we need to create the Prometheus Datasource in order to connect Grafana to Prometheus

Click the Grafana Menu at the top left corner (looks like a fireball)
Click Data Sources
Click the green button Add Data Source.
```

```bash
#Alerts
View Prometheus alerts http://<Host IP Address>:9090/alerts

High load test alert - docker run --rm -it busybox sh -c "while true; do :; done"

Let this run for a few minutes and you will notice the load alert appear. Then Ctrl+C to stop this container.

#Grafana Dashboard
I have imported a Grafana Dashboard template to show the dashboard
```
