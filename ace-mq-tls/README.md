# ACE and MQ (TLS) Connection

# Setup MQ

Create MQ certificates (KDB, RDB, STH):

# External Cluster Access for MQ
add video link
SNI mapping hostname with port 443

ACE properties
<ul>
<li> Queue Name: IN.PERSIST </li>
<li> Connection: MQ client connection properties </li>
<li> Destination queue manager name: hasingle </li>
<li> Queue manager host name: mq-dev-ha-single-ibm-mq-qm-cp4i.apps.ctocp44.ocp.csplab.local (newly-created-route) </li>
<li> Listener port number: 443 </li>
<li> Channel name: HASINGLE.CONN </li>
<li> SSL: True </li>
<li> SSL cipher specification: ANY_TLS12 </li> 
</ul>

# Internal Cluster Access for MQ
If App Connect Dashboard and MQ are deployed on the same cluster then you can use service name to establish connection between them
Here are the ACE properties: <br/>
<ul>
<li> Queue Name: IN.PERSIST </li>
<li> Connection: MQ client connection properties </li>
<li> Destination queue manager name: hasingle </li>
<li> Queue manager host name: ha-single-ibm-mq (queue-manager-service-name) </li>
<li> Listener port number: 1414 </li>
<li> Channel name: HASINGLE.CONN </li>
<li> SSL: True </li>
<li> SSL cipher specification: ANY_TLS12 </li> 
</ul>

### Important:
 * **You DO NOT need SNI mapping for service name with port 1414**
 * If App Connect and MQ are on the same cluster but different namespace then you have to provide \<your-service-name\>.\<your-namespace\>.svc.cluster.local 

# Different users in MQ
johndoe vs aceuser
