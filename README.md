## Metrics of a running server (Metricbeat version)

To solve this problem I would use the Elastic stack. I would deploy Metricbeat on the servers to be monitored, and configure them to ship logs to Elasticsearch, and then use Kibana for visualisation. The implementation below:

Using git, clone the repository:

<pre><code>git clone https://github.com/afoix/metricsbeat-demo.git</pre></code>

Then 

<pre><code>cd metricsbeat-demo</pre></code>

to navigate into the folder. Then run:

<pre><code>docker-compose up</pre></code>

to launch the demo applications. Wait approximately 2 minutes for the applications to finish launching and for data to begin being collected.

Then browse to ``http://localhost:5601/`` and define a Kibana index pattern of ``metricbeat-*`` with time series field @timestamp. Then go to the 'Discover' tab and you should see events that include the reported values. The requested metrics are reported as:

* CPU Utilization: system.cpu.total.pct 
* Free memory: system.memory.free
* Disk space: sytem.filesystem.free

In addition to viewing the raw values in the Discover tab, graphs can be set up for these values in the Visualization tab to help see how they are changing over time.

// TODO Improve the exercises with different mecamisnims.
// Upgrade the version of the project

