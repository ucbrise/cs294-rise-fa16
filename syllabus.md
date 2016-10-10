---
layout: page
title: "Syllabus"
description: "Course Syllabus"
group: navigation
order: 2
---
{% include JB/setup %}

This is a table containing items covered in the class.

{% assign counter = 1 %}

<table class="table table-striped">
   <colgroup>
      <col class="col-md-1">
      <col class="col-md-2">
      <col class="col-md-9">
   </colgroup>
<thead>
   <tr>
      <th> Week </th>
      <th> Date </th>
      <th> Topic </th>
   </tr>
</thead>
<tbody>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td>  08/29/2016 </td>
      <td>
         <h4> Course Overview (Ion, Raluca, Joe, and Joey) </h4>
         <p> In the first class we will outline the focus of the RISE Lab course, identify some of the key questions we will explore, and review some of the key solutions today. </p>

         <h5>Slides </h5>
         <ul>
         <li> Overview [<a href="{{ site.baseurl }}/assets/slides/rise_overview.pptx">pptx</a>, <a href="{{ site.baseurl }}/assets/slides/rise_overview.pdf">pdf</a>]</li>
         <li> Machine Learning in RISE [<a href="{{ site.baseurl }}/assets/slides/rise_ml.pptx">pptx</a>, <a href="{{ site.baseurl }}/assets/slides/rise_ml.pdf">pdf</a>]</li>
         </ul>

      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td>  09/5/2016 </td>
      <td>
         <h4> Class Canceled for Holiday </h4>
         <center><h3>Topic Presentations Selected</h3></center>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td>  09/12/2016 </td>
      <td>
         <h4>
            <a href="{{ site.baseurl }}/rendezvous.html">
            Data-Centric Programming (Joe)
            </a>
         </h4>
         <p>
            Computer scientists have figured out how to build scalable distributed systems for analyzing data in parallel. But we haven't really cracked the general-purpose distributed programming problem. Could we translate our success with distributed data analytics back to solve the "hard parts" of distributed programming? Today we'll dig deep into that question.
         </p>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 09/19/2016 </td>
      <td>
         <h4>
            <a href="{{ site.baseurl }}/trusted_hardware.html">
            Trusted Hardware and Cloud Security (Raluca)
            </a>
         </h4>
         <p>
            We will learn about a new trusted hardware proposal from Intel, SGX. Moreover, we will see how one can protect the confidentiality
            and integrity of the data and computation from a compromised cloud provider using Intel SGX (as in the Haven system). This area is fascinating because it enables a (compromised) cloud provider to run complex systems such as databases without ever seeing the data or the computation it is running, and without being able to cheat in the process. Even if attackers obtain root access on the cloud provider's machines, they won't see the data or affect the correctness of the computation.
         </p>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 09/26/2016 </td>
       <td>
         <h4>
            <a href="{{ site.baseurl }}/cluster_management.html">
            Cluster Management Systems (Ion)
            </a>
         </h4>
         <p>
            In this lecture we will learn about cluster management systems. The role of a cluster management system is to allow different cluster computing frameworks (e.g., Hadoop MR, Spark, Web services) to share the same clusters. Challenges the cluster management systems need to address include performance isolation, the ability to implement various allocation polices, and the ability to scale to thousands of servers and beyond.
         </p>
         <center><h3>Project Ideas Posted</h3></center>
         <p>
            A complete set of project ideas will be posted here.  If you have any suggestions for ideas that you would like collaborators on please add them by sending a pull request.
         </p>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 10/3/2016 </td>
      <td> <!-- (Joe is Absent) -->
         <h4>
            <a href="{{ site.baseurl }}/prediction_serving.html">
            Prediction Serving and the Machine Learning Life-cycle (Joey)
            </a>
         </h4>
         <p>
            In this lecture we will explore the challenges of serving low-latency predictions at scale and managing the machine learning life-cycle spanning model training and management.
         </p>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 10/10/2016 </td>
      <td>
         <h4>
            <a href="{{ site.baseurl }}/robust_ml.html">
            Guest Speaker: Moritz Hardt
            </a>
         </h4>
         <p>
            Moritz will talk about work on new tools for reliable data science.
         </p>
         <center><h3>
            Project Team Selections
         </h3>
         <h4> Please enter your project selections <a href="https://goo.gl/forms/8ztsmJsj6Bp2wuyA2">in this form</a>. </h4>
         </center>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 10/17/2016 </td>
      <td>
         <center><h3> Project Proposal Presentations </h3></center>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 10/24/2016 </td>
      <td> <!-- (Joe is Absent) -->
         <h4>
            <a href="{{ site.baseurl }}/trusted_hardware2.html">
               Securing Distributed Computation and Leakage Vectors (Raluca)
            </a>
         </h4>
         <p>
            We discuss how we to use SGX to secure distributed systems such as MapReduce (the VC3 system): the cloud performs the MapReduce computations without seeing the data or being able to tamper with the computation. Then, we will discuss various types of leakage in SGX and approaches (such as ORAM and GhostRider) to address these issues.
         </p>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 10/31/2016 </td>
       <td> <!-- (Joe is Absent) -->
         <h4>
            <a href="{{ site.baseurl }}/deep_learning.html">
               Overview of Deep Learning (Joey)
            </a>
         </h4>
         <p>
            This lecture will cover an overview of developments in deep learning and then we will dive into several recent papers on  developments in deep learning related to model compression, time-series modeling, as well as serving deep models.
         </p>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 11/7/2016 </td>
       <td>
         <h4>
            <a href="{{ site.baseurl }}/crypto_systems.html">
               Encrypted data analytics and learning (Raluca)
            </a>
         </h4>
         <p>
            In this lecture, we are looking at a leakage that occurs in a distributed setting, and how we can build systems that are not susceptible to this leakage. We then discuss two systems, one for performing data analytics and one for performing machine learning, both on sensitive data the service provider cannot see.
         </p>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 11/14/2016 </td>
      <td>
         <h4>
            <a href="{{ site.baseurl }}/realtime_systems.html">
               Realtime Systems (Ion)
            </a>
         </h4>
         <p>
            Short summary
         </p>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 11/21/2016 </td>
       <td>
         <h4>
            <a href="{{ site.baseurl }}/bandits_and_rl.html">
               Dealing with Feedback (Joey)
            </a>
         </h4>
         <p>
            This lecture will provide an overview of recent developments in bandit and reinforcement learning techniques.
         </p>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 11/28/2016 </td>
      <td>
         <h4>
            <a href="{{ site.baseurl }}/metadata.html">
               Data Context and Metadata Management (Joe)
            </a>
         </h4>
         <p>
We are missing so much rich contextual metadata in our data analysis projects: what data we have, why we have it, how and by whom it gets used, and how all these aspects evolve over time. This *data context* problem raises interesting systems challenges while also suggesting opportunities for new applications and algorithms to significantly improve the efficiency of data analysts.
         </p>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 12/5/2016 </td>
      <td>
         <h4>RRR Week</h4>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td>  12/12/2016 </td>
      <td>
         <center><h3> Final Project Presentations and Posters (3 Hours+) </h3></center>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td>  12/17/2016 </td>
      <td>
         <center><h3> Projects Due </h3></center>
      </td>
   </tr>

</tbody>
</table>


<!--

A little script to highlight the week that is next

-->
<script type="text/javascript">
var current_date = new Date();
var rows = document.getElementsByTagName("tr");
var finished =  false;
for (var i = 1; i < rows.length && !finished; i++) {
   var r = rows[i];
   var date_text = r.getElementsByTagName("td")[0].textContent;
   var d = new Date(date_text + " 23:59:59");
   if (current_date <= d) {
      finished = true;
      var children = r.childNodes
      children[1].style.background = "red"
   }
}
</script>

