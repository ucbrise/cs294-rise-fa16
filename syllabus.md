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
         <h4> Course Overview </h4>
         <p> In the first class we will outline the focus of the RISE Lab course, identify some of the key questions we will explore, and review some of the key solutions today. </p>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td>  09/5/2016 </td>
      <td> 
         <center><h4> Class Canceled for Holiday </h4></center>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td>  09/12/2016 </td>
      <td> 
      TBD (Joe is absent)
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 09/19/2016 </td>
      <td> 
      TBD
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 09/26/2016 </td>
      <td> 
      TBD (Joe is absent)
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 10/3/2016 </td>
      <td> <!-- (Joe is Absent) --> 
         <h4>
         <a href="{{ site.baseurl }}/prediction_serving.html"> 
         Prediction Serving and Managing the Machine Learning Life-cycle
         </a>
         </h4>

         <p>In this lecture we will explore the bigger machine learning life-cycle and discuss the challenges around serving predictions.</p>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 10/10/2016 </td>
      <td> 
      TBD 
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 10/17/2016 </td>
      <td> 
      TBD (Joe is Absent)
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 10/24/2016 </td>
      <td> 
      TBD (Joe is Absent)
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 10/31/2016 </td>
      <td> 
      TBD 
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 11/7/2016 </td>
      <td> 
      TBD 
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 11/14/2016 </td>
      <td> 
      TBD 
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 11/21/2016 </td>
      <td> 
      TBD 
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 11/28/2016 </td>
      <td> 
      TBD 
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td> 12/5/2016 </td>
      <td> 
         <center><h4> RRR Week </h4></center>
      </td>
   </tr>
   <tr>
      <th> {{ counter }} {% assign counter = counter | plus: 1 %} </th>
      <td>  12/12/2016 </td>
      <td> 
         <center><h4> Final Project Presentations </h4></center>
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
   var d = new Date(date_text);
   if (current_date < d) {
      finished = true;
      var children = r.childNodes
      children[1].style.background = "red"
   } 
}
</script>

