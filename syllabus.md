---
layout: page
title: "Syllabus"
description: "Course Syllabus"
group: navigation
order: 2
---
{% include JB/setup %}

This is a table containing items covered in the class.



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
   <tr id="8/29/2016">
      <th> 1 </th>
      <td>  8/29/2016 </td>
      <td> 
         <h4> Course Overview </h4>
         <p> In the first class we will outline the focus of the RISE Lab course, identify some of the key questions we will explore, and review some of the key solutions today. </p>
      </td>
   </tr>
   <tr id="9/5/2016">
      <th> 2 </th>
      <td>  9/5/2016 </td>
      <td> 
         <center><h4> Class Canceled for Holiday </h4></center>
      </td>
   </tr>
   <tr id="9/12/2016">
      <th> 3 </th>
      <td>  9/12/2016 </td>
      <td> 
      TBD (Joe is absent)
      </td>
   </tr>
   <tr id="9/19/2016">
      <th> 4 </th>
      <td> 9/19/2016 </td>
      <td> 
      TBD
      </td>
   </tr>
   <tr id="9/26/2016">
      <th> 5 </th>
      <td> 9/26/2016 </td>
      <td> 
      TBD (Joe is absent)
      </td>
   </tr>
   <tr id="10/3/2016">
      <th> 6 </th>
      <td> 10/3/2016 </td>
      <td> 
      TBD (Joe is Absent)
      </td>
   </tr>
   <tr id="10/10/2016">
      <th> 7 </th>
      <td> 10/10/2016 </td>
      <td> 
      TBD 
      </td>
   </tr>
   <tr id="10/17/2016">
      <th> 8 </th>
      <td> 10/17/2016 </td>
      <td> 
      TBD (Joe is Absent)
      </td>
   </tr>
   <tr id="10/24/2016">
      <th> 9 </th>
      <td> 10/24/2016 </td>
      <td> 
      TBD (Joe is Absent)
      </td>
   </tr>
   <tr id="10/31/2016">
      <th> 10 </th>
      <td> 10/31/2016 </td>
      <td> 
      TBD 
      </td>
   </tr>
   <tr id="11/7/2016">
      <th> 11 </th>
      <td> 11/7/2016 </td>
      <td> 
      TBD 
      </td>
   </tr>
   <tr id="11/14/2016">
      <th> 12 </th>
      <td> 11/14/2016 </td>
      <td> 
      TBD 
      </td>
   </tr>
   <tr id="11/21/2016">
      <th> 13 </th>
      <td> 11/21/2016 </td>
      <td> 
      TBD 
      </td>
   </tr>
   <tr id="11/28/2016">
      <th> 14 </th>
      <td> 11/28/2016 </td>
      <td> 
      TBD 
      </td>
   </tr>
   <tr id="12/5/2016">
      <th> 15 </th>
      <td> 12/5/2016 </td>
      <td> 
         <center><h4> RRR Week </h4></center>
      </td>
   </tr>
   <tr id="12/5/2016">
      <th> 16 </th>
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
var i = 1;
while (!finished) {
   var r = rows[i];
   var d = new Date(r.id);
   if (current_date < d) {
      finished = true;
      var children = r.childNodes
      children[1].style.background = "red"
   } else {
      i++;
   }
}
</script>

