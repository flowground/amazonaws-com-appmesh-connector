# ![LOGO](logo.png) AWS App Mesh **flow**ground Connector

## Description

A generated **flow**ground connector for the AWS App Mesh API (version 2019-01-25).

Generated from: https://api.apis.guru/v2/specs/amazonaws.com/appmesh/2019-01-25/swagger.json<br/>
Generated at: 2019-07-08T14:12:24+03:00

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

### ListMeshes
> Returns a list of existing service meshes.<br/>

#### Input Parameters
* `limit` - _optional_ - Pagination limit<br/>
* `nextToken` - _optional_ - Pagination token<br/>
* `X-Amz-Content-Sha256` - _optional_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### CreateMesh
<blockquote><p>Creates a new service mesh. A service mesh is a logical boundary for network traffic
         between the services that reside within it.</p>
         <p>After you create your service mesh, you can create virtual services, virtual nodes,
         virtual routers, and routes to distribute traffic between the applications in your
         mesh.</p></blockquote>

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

### DeleteMesh
<blockquote><p>Deletes an existing service mesh.</p>
         <p>You must delete all resources (virtual services, routes, virtual routers, virtual nodes)
         in the service mesh before you can delete the mesh itself.</p></blockquote>

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

### DescribeMesh
> Describes an existing service mesh.<br/>

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

### ListVirtualNodes
> Returns a list of existing virtual nodes.<br/>

#### Input Parameters
* `limit` - _optional_ - Pagination limit<br/>
* `nextToken` - _optional_ - Pagination token<br/>
* `meshName` - _required_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### CreateVirtualNode
<blockquote><p>Creates a new virtual node within a service mesh.</p>
         <p>A virtual node acts as logical pointer to a particular task group, such as an Amazon ECS
         service or a Kubernetes deployment. When you create a virtual node, you must specify the
         DNS service discovery hostname for your task group.</p>
         <p>Any inbound traffic that your virtual node expects should be specified as a
            <code>listener</code>. Any outbound traffic that your virtual node expects to reach
         should be specified as a <code>backend</code>.</p>
         <p>The response metadata for your new virtual node contains the <code>arn</code> that is
         associated with the virtual node. Set this value (either the full ARN or the truncated
         resource name, for example, <code>mesh/default/virtualNode/simpleapp</code>, as the
            <code>APPMESH_VIRTUAL_NODE_NAME</code> environment variable for your task group's Envoy
         proxy container in your task definition or pod spec. This is then mapped to the
            <code>node.id</code> and <code>node.cluster</code> Envoy parameters.</p>
         <note>
            <p>If you require your Envoy stats or tracing to use a different name, you can override
            the <code>node.cluster</code> value that is set by
               <code>APPMESH_VIRTUAL_NODE_NAME</code> with the
               <code>APPMESH_VIRTUAL_NODE_CLUSTER</code> environment variable.</p>
         </note></blockquote>

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

### DeleteVirtualNode
<blockquote><p>Deletes an existing virtual node.</p>
         <p>You must delete any virtual services that list a virtual node as a service provider
         before you can delete the virtual node itself.</p></blockquote>

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

### DescribeVirtualNode
> Describes an existing virtual node.<br/>

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

### UpdateVirtualNode
> Updates an existing virtual node in a specified service mesh.<br/>

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

### ListRoutes
> Returns a list of existing routes in a service mesh.<br/>

#### Input Parameters
* `limit` - _optional_ - Pagination limit<br/>
* `nextToken` - _optional_ - Pagination token<br/>
* `meshName` - _required_
* `virtualRouterName` - _required_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### CreateRoute
<blockquote><p>Creates a new route that is associated with a virtual router.</p>
         <p>You can use the <code>prefix</code> parameter in your route specification for path-based
         routing of requests. For example, if your virtual router service name is
            <code>my-service.local</code>, and you want the route to match requests to
            <code>my-service.local/metrics</code>, then your prefix should be
         <code>/metrics</code>.</p>
         <p>If your route matches a request, you can distribute traffic to one or more target
         virtual nodes with relative weighting.</p></blockquote>

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

### DeleteRoute
> Deletes an existing route.<br/>

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

### DescribeRoute
> Describes an existing route.<br/>

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

### UpdateRoute
> Updates an existing route for a specified service mesh and virtual router.<br/>

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

### ListVirtualRouters
> Returns a list of existing virtual routers in a service mesh.<br/>

#### Input Parameters
* `limit` - _optional_ - Pagination limit<br/>
* `nextToken` - _optional_ - Pagination token<br/>
* `meshName` - _required_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### CreateVirtualRouter
<blockquote><p>Creates a new virtual router within a service mesh.</p>
         <p>Any inbound traffic that your virtual router expects should be specified as a
            <code>listener</code>. </p>
         <p>Virtual routers handle traffic for one or more service names within your mesh. After you
         create your virtual router, create and associate routes for your virtual router that direct
         incoming requests to different virtual nodes.</p></blockquote>

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

### DeleteVirtualRouter
<blockquote><p>Deletes an existing virtual router.</p>
         <p>You must delete any routes associated with the virtual router before you can delete the
         router itself.</p></blockquote>

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

### DescribeVirtualRouter
> Describes an existing virtual router.<br/>

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

### UpdateVirtualRouter
> Updates an existing virtual router in a specified service mesh.<br/>

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

### ListVirtualServices
> Returns a list of existing virtual services in a service mesh.<br/>

#### Input Parameters
* `limit` - _optional_ - Pagination limit<br/>
* `nextToken` - _optional_ - Pagination token<br/>
* `meshName` - _required_
* `X-Amz-Date` - _optional_
* `X-Amz-Algorithm` - _optional_
* `X-Amz-Credential` - _optional_
* `X-Amz-Security-Token` - _optional_
* `X-Amz-Signature` - _optional_
* `X-Amz-SignedHeaders` - _optional_

### CreateVirtualService
<blockquote><p>Creates a virtual service within a service mesh.</p>
         <p>A virtual service is an abstraction of a real service that is either provided by a
         virtual node directly, or indirectly by means of a virtual router. Dependent services call
         your virtual service by its <code>virtualServiceName</code>, and those requests are routed
         to the virtual node or virtual router that is specified as the provider for the virtual
         service.</p></blockquote>

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

### DeleteVirtualService
> Deletes an existing virtual service.<br/>

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

### DescribeVirtualService
> Describes an existing virtual service.<br/>

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

### UpdateVirtualService
> Updates an existing virtual service in a specified service mesh.<br/>

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

**flow**ground :- Telekom iPaaS / amazonaws-com-appmesh-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
