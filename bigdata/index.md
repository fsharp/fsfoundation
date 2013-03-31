---
layout: page
title: Cloud Programming | The F# Software Foundation
headline: Scalable Data, Compute and Messaging with F#
---

This is an overview of the packages and tools for scalable data processing with F#,
particularly for taking advantage of scalable cloud-computing resources.

Data processing commonly follows a functional (as opposed to an imperative) model. 
F#'s functional-first design makes data processing pipelines very natural. The Type Provider feature of 
F# 3.0 makes F# a powerful solution for accessing both regular and irregular data, including traditional databases,
web-scale ontologies and standard structured text formats like JSON, and XML.

Scalable distributed calculations also tend to be a very good fit for functional languages in 
general and particularly F# due to the wide variety of libraries and services available. The 
[F# Maths](../math/index.html) page surveys available numerics packages. 

## Cloud Programming

### [Windows Azure](http://www.windowsazure.com/en-us/home/features/overview/)

Windows Azure provides access to  Microsoft's worldwide datacenters through services including 
virtual machines, geo-redundant storage, database clusters and website deployment.  
[This page](http://www.windowsazure.com/en-us/develop/net/fundamentals/compute/) provides 
detail on the structure of Azure applications.

Below are resources on using Windows Azure from F# and .NET in general:
 * [Introduction to Windows Azure](http://www.windowsazure.com/en-us/develop/net/fundamentals/intro-to-windows-azure/)
 * [.NET and RESTful management API reference](http://msdn.microsoft.com/en-us/library/windowsazure/ff800682.aspx)
 * [Publishing an F#/C# MVC Application to Windows Azure](http://msdn.microsoft.com/en-us/library/vstudio/jj865569.aspx) 
 * [Distributed Numerics on Azure with F#](http://blogs.msdn.com/b/cloudnumerics/archive/2012/01/16/cloud-numerics-example-distributed-numerics-on-azure-with-f.aspx)
 * [How to use Hadoop on Azure](http://www.windowsazure.com/en-us/develop/net/how-to-guides/hadoop/)


### [Amazon Web Services](http://aws.amazon.com)
Amazon Web Services (AWS) provide a large array of on-demand and managed computing and 
hosting services. AWS include on-demand and reserved virtual machine instances, 
a variety of storage options, a content delivery network (CDN), DNS capabilities, and many others. 
Amazon offers services from multiple data centers around the world.

Amazon offers a .NET SDK for managing the AWS services, 
[described here](http://aws.amazon.com/sdkfornet/). This SDK provides facilities for managing 
storage, compute instances, and other Amazon services.

Some additional resources for using F# and .NET on Amazon's AWS service:
 * [AWS Toolkit for Visual Studio](http://aws.amazon.com/visualstudio/)
 * [Using F# and C# with Elastic MapReduce](http://atbrox.com/2011/02/07/an-example-of-using-f-and-c-netmono-with-amazons-elastic-mapreduce-hadoop/)

## Distributed Communications

Distributed compute problem require a very wide range of communication capabilities, ranging
from simple command line argument passing to heavily optimized, low-latency interprocess
communications. This section lists a wide range of communication libraries available to F#.

 * [F# Mailbox Processor](http://blogs.msdn.com/b/dsyme/archive/2010/02/15/async-and-parallel-design-patterns-in-f-part-3-agents.aspx) - Discusses the Agent pattern for inter-thread and inter-process communication using the F# library's MailboxProcessor. 
 * [ServiceStack](http://www.servicestack.net/) - "Thoughtfully architected, obscenely fast, thoroughly enjoyable web services for all", see also [F# web programming](http://fsharp.org/webstacks/index.html)
 * [F# ZeroMQ bindings](https://github.com/pblasucci/fs-zmq) - An F#-specific binding for the [ZeroMQ](http://www.zeromq.org) (Zero Message Queue) library.
 * [ZeroMQ](http://www.zeromq.org/bindings:clr) - A more general .NET binding for ZeroMQ.
 * [MPI .NET](http://osl.iu.edu/research/mpi.net/) - A C# implementation of the popular [Message Passing Interface (MPI) protocol](http://en.wikipedia.org/wiki/Message_Passing_Interface).  
 * [MS-MPI](http://msdn.microsoft.com/en-us/library/bb524831.aspx) - Microsoft's implementation of the MPI protocol, available on some versions of Windows Server.
 * [Windows Communication Foundation](http://msdn.microsoft.com/en-us/library/dd456779.aspx) - A framework from Microsoft for building service-oriented applications.


## NoSQL Databases

[Cassandra](http://cassandra.apache.org/):

 * [Aquiles](http://aquiles.codeplex.com/)
 * [Cassandraemon](http://cassandraemon.codeplex.com/)
 * [cassandra-sharp](http://code.google.com/p/cassandra-sharp/)
 * [FluentCassandra](https://github.com/managedfusion/fluentcassandra)

[RavenDB](http://ravendb.net/):

 * [F# Client API](http://ravendb.net/docs/client-api/fsharp) The F# client API is a thin wrapper around the standard RavenDB client API, that provides a small set of combinators and a computation builder that hides the complexity of dealing with Linq expressions from F#. This documentation assumes some familiarity with the basics of RavenDB. 


[MongoDB](http://www.mongodb.org/):

 * [Mongo DB](http://www.mongodb.org/display/DOCS/CSharp+Language+Center) bindings for .NET

[Neo4j](http://www.neo4j.org/):

 * [Neo4jClient](http://hg.readify.net/neo4jclient/wiki/Home) - Neo4j bindings for .NET


## Other links
 * [Parallel LINQ (PLINQ)](http://msdn.microsoft.com/en-us/library/dd460688.aspx)
 * [Microsoft .NET SDK for Hadoop](http://hadoopsdk.codeplex.com/)
 * [F# Data Mining](http://fdatamining.blogspot.com/2010/05/why-f-is-language-for-data-mining.html)
 * [Parallel Programming in F# III: Aggregating Data:](http://tomasp.net/blog/fsharp-parallel-aggregate.aspx)
