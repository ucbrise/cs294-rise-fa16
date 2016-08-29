---
layout: masthead_page
title: CS294 RISE
tagline: <big><b>R</b></big>eal-time, <big><b>I</b></big>ntelligent, and <big><b>S</b></big>ecure <big><b>E</b></big>xecution
mastimage: /assets/images/rise_cloud.jpg
---
{% include JB/setup %}




<!--
 Relative links:
   link to readings [pages](reading)
   relative path of site {{ site.baseurl }}

 Running jekyll serve locally:

    bundle exec jekyll serve --baseurl ''

 liquid programming example (we should never really need this):

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>


 -->

**Mondays from 3:30 to 5:30 in Soda 405**


### Course Overview

This seminar aims to serve as a catalyst for research in the RISE lab, the new lab following the AMPLab. We will read and discuss papers on the state-of-the-art of learning systems (large-scale model training, deep learning, real-time robust inference), big data systems (scale-out vs scale-up, scalable data analytics), and systems security (computation on encrypted data, secure hardware enclaves, language-based mechanisms).
Because this is a research class we have capped the enrollment at 30 students.

An important component of the class will be the final project aiming at original research in this space.
In addition, students will be required to present several papers throughout the year.  We  expect students to attend every lecture and actively participate in conversation about the papers.

The course website for this class is being hosted on GitHub pages.
If you see any errors or omissions or would like to contribute content or suggested reading to any of the discussion topics please consider emailing us or sending a pull request to this [GitHub repository](https://github.com/ucbrise/cs294-rise-fa16/tree/gh-pages).

### Grading Policy

||:-:  | | ---  ||
|| **40%** | | Class Participation -- answer questions, join discussion, and present papers  ||
|| **10%** | | Initial Project Proposal Presentation ||
|| **25%** | | Project Presentations   ||
|| **25%** | | Final Project Report   ||
 




## The RISE Research Vision

The development of open source big data processing systems, such as Hadoop, Hive, Storm, and more recently Spark and Kafka have fundamentally transformed daily practices in business and science.
These systems have enabled the creation of new business models (e.g., Facebook, Twitter), the disruption of existing industries (e.g, Amazon, Uber, and Airbnb), and rapid progress in scientific research (e.g., genomics, astronomy, biology).
Today, we are finding ourselves at another inflection point in big data processing that will define the next decade. This change is driven by three trends:

1. Our world is becoming ever more connected, with sensors embedded in buildings, appliances, engines, clothes, and more.
Connected to the Internet, these sensors observe the world around us in **real-time** at unprecedented **scale**.

1. With the advent of drones, self-driving cars, and smart buildings and infrastructure we are now able not only to observe, but to make **automated decisions** that impact the physical world.

1. The success of applications such as high-frequency trading and computational advertising have demonstrated the tremendous value of making **real-time decisions** on **live data**.

These trends give us a glimpse of a future in which we can sense the world around us, ingest information, analyze it, and make automated decisions in real-time.
The ability to make decisions on live data can fundamentally change the way we interact with the physical word, and accelerate scientific discovery by enabling rapid exploration and testing of a solution space.
This would enable a new categories of applications that were not possible before, such as zero-time defense against Internet attacks, coordinated fleets of drones, real-time infectious disease diagnosis and tracking, early earthquake response, and many others.

To realize this grand promise we need to develop new open source software tools, algorithms, and hardware that will power the next generation of data applications---the same way Hadoop, and more recently Spark, have powered big data analytics over the past decade. This will require us to pursue significant advances in three areas:

1. **Systems:** Build scalable data analytics tools that provide orders-of-magnitude lower latency and higher throughput than existing platforms, such as Spark. These tools must be able to close the loop between data, models, and decisions reliably and at scale.
<!-- The tools must be able to form asynchronous, closed-loop flows: from signals to models to actuation back to signals, without pausing for compute barriers or expensive coordination. -->

1. **Machine Learning:** Develop on-line machine learning algorithms that are robust to noisy data and unforeseen inputs and capable of responding in real-time.
<!-- These requirements are essential in new applications such defending cyber infrastructure or operating a fleet of autonomous vehicles. -->

1. **Security:** Ensure user privacy and application security without impacting functionality or performance. Many real-time applications touch sensitive data and co-exist with humans in physical space, implying significant risks of privacy breaches and potential physical harm.
<!-- By ensuring privacy and security without compromising functionality, we will enable new applications. Today, new applications are increasingly incubated in public clouds to take advantage of elasticity and cost effectiveness. Unfortunately this exposes these sensitive applications to security risks and limitations: cloud-wide security leaks, malicious employees of cloud infrastructure, and regulatory restrictions on public cloud usage.  As the value of these applications increases, providing strong security becomes a necessity. Furthermore, strong privacy will increase the value delivered by these applications, as it will incentivize more users to use them. -->


While there exist a few solutions that make real-time decisions on live data, notably in the domains of high-frequency trading and ad bidding, these solutions are highly specialized (on-off), and have taken years and huge resources to develop.
The goal of the RISE Lab is to dramatically lower the barrier of building such solutions by developing a general-purpose secure real-time decision stack (SRDS).
SRDS will enable many more people to build sophisticated decision and predictive analytics applications which will fundamentally change the way we interact with our world, and unlock massive value from the ever increasing amount of data collected by individuals and organizations alike.

Enabling real-time decisions on live data will lead to a phase transition in data processing, similar to the transition from small to big data.
Just as big data led to dramatically better results even when using traditional algorithms, we believe that real-time processing on live data will lead to qualitatively superior results, by enabling rapid exploration of the search space and continuous adaptation to changes in the environment (e.g., enabling large-scale, reinforced learning in real time).


### Undergraduate Enrollment Instructions

Strong undergraduates with an interest in research and good grades are encouraged to enroll in this class.
To get permission to enroll in CS294 RISE please email the instructors a copy of your transcript and description of any prior research experience.

## Instructors

<!-- The following block is for faculty info -->
<div class="container-fluid">
  <script type="text/javascript">
    function email_address(name) {
      domain = 'cs.berkeley';
      tld = 'edu';
      document.write(
        '<a href="mailto:' + name + '@' + domain + '.' + tld + '">' +
        name + '@' + domain + '.' + tld + '</a>');
  }
  </script>
  <div class="row">
    <div class="col-sm-3"><div class="text-center">
      <img src="https://jegonzal.github.io/assets/jegonzal.jpg" alt="Joey Gonzalez" style="height: 150px;"/>
      <address>
        <strong>Joseph E. Gonzalez</strong><br>
        <script type="text/javascript"> email_address("jegonzal") </script>
      </address>
    </div></div>
    <div class="col-sm-3"><div class="text-center">
      <img src="https://www2.eecs.berkeley.edu/Faculty/Photos/Homepages/hellerstein.jpg" alt="Joseph Hellerstein" style="height: 150px;"/>
      <address>
        <strong>Joseph Hellerstein</strong><br>
        <script type="text/javascript"> email_address("hellerstein") </script>
      </address>
    </div></div>
    <div class="col-sm-3"><div class="text-center">
      <img src="https://www2.eecs.berkeley.edu/Faculty/Photos/Homepages/ralucap.jpg" alt="Raluca Ada Popa" style="height: 150px;"/>
      <address>
        <strong>Raluca Ada Popa</strong><br>
        <script type="text/javascript"> email_address("raluca.popa") </script>
      </address>
    </div></div>
    <div class="col-sm-3"><div class="text-center">
      <img src="https://people.eecs.berkeley.edu/~istoica/ion_picture_small.jpg " alt="Ion Stoica" style="height: 150px;"/>
      <address>
        <strong>Ion Stoica</strong><br>
        <script type="text/javascript"> email_address("istoica") </script>
      </address>
    </div></div>
  </div>
</div>


<!-- | <img src="https://jegonzal.github.io/assets/jegonzal.jpg" alt="Joey Gonzalez" style="height: 150px;"/> | <img src="https://www2.eecs.berkeley.edu/Faculty/Photos/Homepages/hellerstein.jpg" alt="Joseph Hellerstein" style="height: 150px;"/> | <img src="https://people.eecs.berkeley.edu/~raluca/RalucaPreVeil.jpg" alt="Raluca Ada Popa" style="height: 150px;"/> | <img src="https://people.eecs.berkeley.edu/~istoica/ion_picture_small.jpg " alt="Ion Stoica" style="height: 150px;"/> |
|:-:|:-:|:-:|:-:|
| Joseph E. Gonzalez | Joe Hellerstein | Raluca Ada Popa | Ion Stoica |
| <script type="text/javascript"> email_address("jegonzal") </script>| <script type="text/javascript"> email_address("hellerstein") </script>| <script type="text/javascript"> email_address("raluca.popa") </script> | <script type="text/javascript"> email_address("istoica") </script> | -->




