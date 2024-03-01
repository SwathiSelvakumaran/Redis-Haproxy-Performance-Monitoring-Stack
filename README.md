# System-performance-metrics-analysis
Steps followed:
Prerequisite:
1. Install logstash,elasticsearch and Kibana on localhost server.
2. Install filebeat for haproxy performance dashboard

Redis performance metrics:
1. Install and configure redis on the local server.
2. configure the redis to send logs to elasticsearch through port 9200.
3. Configure Elasticsearch and Kibana.
4. Access the Kibana dashboard in http://localhost:5601
5. create a new Index pattern by going to Discover -> Create index. The new index pattern will be "redis*".
6. Go to dashboard and create new virtualization.
7. Select the redis index pattern from drop down and analyze the performance metrics by dragging the required fields from the Available fields dropdown.

Performance metrics that can be verified by selecting the attributes:
Memory usage: used_memory, used_memory_peak, and used_memory_lua
CPU usage: used_cpu_sys, used_cpu_user, and used_cpu_sys_children
Latency: latency
Operations per second: instantaneous_ops_per_sec and total_commands_processed
Cache hit rate: keyspace_hits and keyspace_misses
Network throughput: instantaneous_input_kbps and instantaneous_output_kbps
Persistence:  rdb_last_bgsave_time_sec and aof_last_bgrewrite_time_sec

Redis performance metrics dashboard:

![image](https://github.com/SwathiSelvakumaran/System-performance-metrics-analysis/assets/73472775/a24e5360-bb77-42c7-92a4-702b4ef499de)


Haproxy performance metrics:
1. Install and configure haproxy on the local server.
2. create two web servers in the DigitalOcean Droplet. (frontend and backend)
3. Configure the webservers and the log to the haproxy configuration file /etc/haproxy/haproxy.cfg
4. configure the filebeat to fetch logs from haproxy and to send these logs to elasticsearch through port 9200.
3. Configure Elasticsearch and Kibana.
4. Access the Kibana dashboard in http://localhost:5601
5. create a new Index pattern by going to Discover -> Create index. The new index pattern will be "filebeat*".
6. Go to the dashboard and create new virtualization.
7. Select the filebeat index pattern from drop down and analyze the performance metrics by dragging the required fields from the Available fields dropdown.

Performance metrics that can be verified by selecting the attributes:
1. Connections: haproxy.connections.active, haproxy.connections.backend, haproxy.connections.frontend, haproxy.connections.retries, haproxy.connections.server
2. HTTP: haproxy.http.request.captured_cookie, haproxy.http.request.captured_headers, haproxy.http.request.raw_request_line, haproxy.http.request.time_wait_ms
3. Latency: haproxy.total_waiting_time_ms
4. Load balancing: haproxy.server_name, haproxy.server_queue, haproxy.time_queue

![image](https://github.com/SwathiSelvakumaran/System-performance-metrics-analysis/assets/73472775/ece5daac-d989-45cb-a63f-11b8cdc9bee0)

