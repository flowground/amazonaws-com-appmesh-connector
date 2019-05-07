# ![LOGO](logo.png) AWS App Mesh MSP Connector

## Description

A generated MSP connector for the AWS App Mesh API (version 2019-01-25).

Generated from: https://api.apis.guru/v2/specs/amazonaws.com/appmesh/2019-01-25/swagger.json<br/>
Generated at: 2019-05-07T11:15:22+03:00

## API Description

<p>AWS App Mesh is a service mesh based on the Envoy proxy that makes it easy to monitor and
         control containerized microservices. App Mesh standardizes how your microservices
         communicate, giving you end-to-end visibility and helping to ensure high-availability for
         your applications.</p>
         <p>App Mesh gives you consistent visibility and network traffic controls for every
         microservice in an application. You can use App Mesh with Amazon ECS
         (using the Amazon EC2 launch type), Amazon EKS, and Kubernetes on AWS.</p>
         <note>
            <p>App Mesh supports containerized microservice applications that use service discovery
            naming for their components. To use App Mesh, you must have a containerized application
            running on Amazon EC2 instances, hosted in either Amazon ECS, Amazon EKS, or Kubernetes on AWS. For
            more information about service discovery on Amazon ECS, see <a href="http://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-discovery.html">Service Discovery</a> in the
               <i>Amazon Elastic Container Service Developer Guide</i>. Kubernetes <code>kube-dns</code> and
               <code>coredns</code> are supported. For more information, see <a href="https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/">DNS
               for Services and Pods</a> in the Kubernetes documentation.</p>
         </note>

## Authorization

Supported authorization schemes:
- API Key
## Actions

### Returns a list of existing service meshes.

#### Input Parameters
* `limit` - _optional_ - Pagination limit
* `nextToken` - _optional_ - Pagination token
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### <p>Creates a new service mesh. A service mesh is a logical boundary for network traffic<br/>
>          between the services that reside within it.</p><br/>
>          <p>After you create your service mesh, you can create virtual services, virtual nodes,<br/>
>          virtual routers, and routes to distribute traffic between the applications in your<br/>
>          mesh.</p>

#### Input Parameters
* `Action` - _required_
* `Version` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### <p>Deletes an existing service mesh.</p><br/>
>          <p>You must delete all resources (virtual services, routes, virtual routers, virtual nodes)<br/>
>          in the service mesh before you can delete the mesh itself.</p>

#### Input Parameters
* `meshName` - _required_
* `Version` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Describes an existing service mesh.

#### Input Parameters
* `meshName` - _required_
* `Version` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Returns a list of existing virtual nodes.

#### Input Parameters
* `limit` - _optional_ - Pagination limit
* `nextToken` - _optional_ - Pagination token
* `meshName` - _required_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### <p>Creates a new virtual node within a service mesh.</p><br/>
>          <p>A virtual node acts as logical pointer to a particular task group, such as an Amazon ECS<br/>
>          service or a Kubernetes deployment. When you create a virtual node, you must specify the<br/>
>          DNS service discovery hostname for your task group.</p><br/>
>          <p>Any inbound traffic that your virtual node expects should be specified as a<br/>
>             <code>listener</code>. Any outbound traffic that your virtual node expects to reach<br/>
>          should be specified as a <code>backend</code>.</p><br/>
>          <p>The response metadata for your new virtual node contains the <code>arn</code> that is<br/>
>          associated with the virtual node. Set this value (either the full ARN or the truncated<br/>
>          resource name, for example, <code>mesh/default/virtualNode/simpleapp</code>, as the<br/>
>             <code>APPMESH_VIRTUAL_NODE_NAME</code> environment variable for your task group's Envoy<br/>
>          proxy container in your task definition or pod spec. This is then mapped to the<br/>
>             <code>node.id</code> and <code>node.cluster</code> Envoy parameters.</p><br/>
>          <note><br/>
>             <p>If you require your Envoy stats or tracing to use a different name, you can override<br/>
>             the <code>node.cluster</code> value that is set by<br/>
>                <code>APPMESH_VIRTUAL_NODE_NAME</code> with the<br/>
>                <code>APPMESH_VIRTUAL_NODE_CLUSTER</code> environment variable.</p><br/>
>          </note>

#### Input Parameters
* `meshName` - _required_
* `Version` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### <p>Deletes an existing virtual node.</p><br/>
>          <p>You must delete any virtual services that list a virtual node as a service provider<br/>
>          before you can delete the virtual node itself.</p>

#### Input Parameters
* `meshName` - _required_
* `virtualNodeName` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Describes an existing virtual node.

#### Input Parameters
* `meshName` - _required_
* `virtualNodeName` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Updates an existing virtual node in a specified service mesh.

#### Input Parameters
* `meshName` - _required_
* `virtualNodeName` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Returns a list of existing routes in a service mesh.

#### Input Parameters
* `limit` - _optional_ - Pagination limit
* `nextToken` - _optional_ - Pagination token
* `meshName` - _required_
* `virtualRouterName` - _required_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### <p>Creates a new route that is associated with a virtual router.</p><br/>
>          <p>You can use the <code>prefix</code> parameter in your route specification for path-based<br/>
>          routing of requests. For example, if your virtual router service name is<br/>
>             <code>my-service.local</code>, and you want the route to match requests to<br/>
>             <code>my-service.local/metrics</code>, then your prefix should be<br/>
>          <code>/metrics</code>.</p><br/>
>          <p>If your route matches a request, you can distribute traffic to one or more target<br/>
>          virtual nodes with relative weighting.</p>

#### Input Parameters
* `meshName` - _required_
* `virtualRouterName` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Deletes an existing route.

#### Input Parameters
* `meshName` - _required_
* `virtualRouterName` - _required_
* `routeName` - _required_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Describes an existing route.

#### Input Parameters
* `meshName` - _required_
* `virtualRouterName` - _required_
* `routeName` - _required_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Updates an existing route for a specified service mesh and virtual router.

#### Input Parameters
* `meshName` - _required_
* `virtualRouterName` - _required_
* `routeName` - _required_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Returns a list of existing virtual routers in a service mesh.

#### Input Parameters
* `limit` - _optional_ - Pagination limit
* `nextToken` - _optional_ - Pagination token
* `meshName` - _required_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### <p>Creates a new virtual router within a service mesh.</p><br/>
>          <p>Any inbound traffic that your virtual router expects should be specified as a<br/>
>             <code>listener</code>. </p><br/>
>          <p>Virtual routers handle traffic for one or more service names within your mesh. After you<br/>
>          create your virtual router, create and associate routes for your virtual router that direct<br/>
>          incoming requests to different virtual nodes.</p>

#### Input Parameters
* `meshName` - _required_
* `Version` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### <p>Deletes an existing virtual router.</p><br/>
>          <p>You must delete any routes associated with the virtual router before you can delete the<br/>
>          router itself.</p>

#### Input Parameters
* `meshName` - _required_
* `virtualRouterName` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Describes an existing virtual router.

#### Input Parameters
* `meshName` - _required_
* `virtualRouterName` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Updates an existing virtual router in a specified service mesh.

#### Input Parameters
* `meshName` - _required_
* `virtualRouterName` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Returns a list of existing virtual services in a service mesh.

#### Input Parameters
* `limit` - _optional_ - Pagination limit
* `nextToken` - _optional_ - Pagination token
* `meshName` - _required_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### <p>Creates a virtual service within a service mesh.</p><br/>
>          <p>A virtual service is an abstraction of a real service that is either provided by a<br/>
>          virtual node directly, or indirectly by means of a virtual router. Dependent services call<br/>
>          your virtual service by its <code>virtualServiceName</code>, and those requests are routed<br/>
>          to the virtual node or virtual router that is specified as the provider for the virtual<br/>
>          service.</p>

#### Input Parameters
* `meshName` - _required_
* `Version` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Deletes an existing virtual service.

#### Input Parameters
* `meshName` - _required_
* `virtualServiceName` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Describes an existing virtual service.

#### Input Parameters
* `meshName` - _required_
* `virtualServiceName` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### Updates an existing virtual service in a specified service mesh.

#### Input Parameters
* `meshName` - _required_
* `virtualServiceName` - _required_
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

## License

flowground :- Telekom iPaaS / amazonaws-com-appmesh-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
