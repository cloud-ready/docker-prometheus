# docker-prometheus


see: https://yunlzheng.gitbook.io/prometheus-book/part-ii-prometheus-jin-jie/exporter/commonly-eporter-usage/use-prometheus-monitor-container

Get default Prometheus config
```bash
IMAGE="prom/prometheus:${IMAGE_TAG:-v2.5.0}"
CONTAINER_NAME=$(docker inspect --format='{{.Id}}' ${IMAGE} | awk -F: '{print $2}' | cut -c1-8)
docker create --name ${CONTAINER_NAME} ${IMAGE}
docker cp ${CONTAINER_NAME}:/etc/prometheus/prometheus.yml prometheus.yml
docker rm -fv ${CONTAINER_NAME}
```
