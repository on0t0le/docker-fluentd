### Simple fluentd deployment
To start your personal fluentd log-aggregator
```sh
docker-compose up -d
```
After that you will be able to see logs in local *log* folder.
For adding containers to fluentd log-aggregator use flags `--log-driver=fluentd --log-opt tag="docker.{.ID}}" --log-opt fluentd-address=localhost:24224`
Example:
```sh
docker run --log-driver=fluentd --log-opt tag="docker.{.ID}}" --log-opt fluentd-address=localhost:24224 ubuntu echo '...'
```