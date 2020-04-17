---
layout: workshop      # DON'T CHANGE THIS.
venue: "University of Idaho, Institute for Modeling, Collaboration and Innovation (http://imci.uidaho.edu)"        # brief name of host site without address (e.g., "Euphoric State University")
address: "IRIC Building, Room 352, University of Idaho - 875 Perimeter Dr, Moscow, ID 83844"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "us"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
latitude: "46.726960"     # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "-117.010930"    # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "Apr 23-24, 2020"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "8:30am - 4:30pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2020-04-22      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2020-04-24        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Erich Seamon", "Travis Seaborn"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["TBD"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["erichs@uidaho.edu"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes: https://pad.carpentries.org/2020-03-26-uidaho-geospatial             # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
HEADER

Edit the values in the block above to be appropriate for your workshop.
If the value is not 'true', 'false', 'null', or a number, please use
double quotation marks around the value, unless specified otherwise.
And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}



{% comment %}
For a workshop please delete the following block
{% endcomment %}

{% comment %}
Check DC curriculum
{% endcomment %}

{% if site.carpentry == "dc" or site.carpentry == "dc" %}
{% unless site.curriculum == "dc-ecology" or site.curriculum == "dc-genomics" or site.curriculum == "dc-socsci" or site.curriculum == "dc-geospatial" %}
<div class="alert alert-warning">
It looks like you are setting up a website for a Data Carpentry curriculum but you haven't specified the curriculum type in the <code>_config.yml</code> file (current value in <code>_config.yml</code>: "<strong>{{ site.curriculum }}</strong>", possible values: <code>dc-ecology</code>, <code>dc-genomics</code>, <code>dc-socsci</code>, or <code>dc-geospatial</code>). After editing this file, you need to run <code>make serve</code> again to see the changes reflected.
</div>
{% endunless %}
{% endif %}

{% comment %}
EVENTBRITE

This block includes the Eventbrite registration widget if
'eventbrite' has been set in the header.  You can delete it if you
are not using Eventbrite, or leave it in, since it will not be
displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">General Information</h2>

{% comment %}
INTRODUCTION

Edit the general explanatory paragraph below if you want to change
the pitch.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/intro.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/intro.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/intro.html %}
{% endif %}

{% comment %}
AUDIENCE

Explain who your audience is.  (In particular, tell readers if the
workshop is only open to people from a particular institution.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/who.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/who.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/who.html %}
{% endif %}

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://itouchmap.com/latlong.html to find the lat/long of an
address.
{% endcomment %}
{% if page.latitude and page.longitude %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on. They should have a few specific software packages installed (listed <a href="#setup">below</a>).
</p>

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<p id="code-of-conduct">
<strong>Code of Conduct:</strong>  Everyone who participates in Carpentries activities is required to conform to the <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Code of Conduct</a>. This document also outlines how to report an incident if needed.
</p>


{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
</p>

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment %} 
SURVEYS - DO NOT EDIT SURVEY LINKS 
{% endcomment %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop. Please note: we have a Uidaho survey that contains important logistical questions - then Data Carpentry wants you to complete a more demographic focused survey.  Please complete both.</p>
<p><a href="https://docs.google.com/forms/d/1bpvkH3TbaHu62-zZxocTIi4XBAjhcPJIOjRcW_8FjAU/">UIDAHO Pre-workshop Survey - complete by March 16th, 2020</a></p>
<p><a href="{{ site.pre_survey }}{{ site.github.project_title }}">DATA CARPENTRY Pre-workshop Survey</a></p>
<p><a href="{{ site.post_survey }}{{ site.github.project_title }}">DATA CARPENTRY Post-workshop Survey</a></p>

<hr/>


{% comment %}
SCHEDULE

Show the workshop's schedule.  Edit the items and times in the table
to match your plans.  You may also want to change 'Day 1' and 'Day
2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>

{% if site.carpentry == "swc" %}
{% include swc/schedule.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/schedule.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/schedule.html %}
{% endif %}

{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

http://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>

{% comment %}
SYLLABUS

Show what topics will be covered.

1. If your workshop is R rather than Python, remove the comment
around that section and put a comment around the Python section.
2. Some workshops will delete SQL.
3. Please make sure the list of topics is synchronized with what you
intend to teach.
4. You may need to move the div's with class="col-md-6" around inside
the div's with class="row" to balance the multi-column layout.

This is one of the places where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}
<h2 id="syllabus">Syllabus</h2>

{% if site.carpentry == "swc" %}
{% include swc/syllabus.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/syllabus.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/syllabus.html %}
{% endif %}

<hr/>

{% comment %}
SETUP

Delete irrelevant sections from the setup instructions.  Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}

<h2 id="setup">Setup</h2>

<p>
  To participate in a
  {% if site.carpentry == "swc" %}
  Software Carpentry
  {% elsif site.carpentry == "dc" %}
  Data Carpentry
  {% elsif site.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  workshop,
  you will need access to the software described below.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

{% if site.carpentry == "swc" %}
{% include swc/setup.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/setup.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/setup.html %}
{% endif %}

<h2 id="setup">Video Conference Access</h2>

This zoom conference information will be used for both days (April 23rd and 24th) - as well as the prepatory zoom testing, scheduled for Wednesday, April 22nd @ 1pm.  If you would like to test out your zoom settings in advance, please drop onto the call.

A few other zoom/video conferencing housekeeping issues: 

1) If you can use a dual monitor setup, this will greatly assist you.
2) If possible, make sure you have a webcam ergonomically set up level with your face, with your microphone close to you.
3) Please leave your webcam on while interfacing with the workshop.  This is not a requirement.  We realize that you may have additional family or work/class committments that may require you to step away. However, while you are engaged in the workshop, try to have your webcam on!  It will be more fun and engaging! (If you can consider R and geospatial analysis fun!)
4. We will try to leverage zoom as much as possible.  We are not going to use any other software, other than Rstudio and zoom.  However, we will be lecturing using the materials referenced above.  So - following along via your browser with the lesson we are going over will be helpful.  That means: Rstudio + zoom + web browser.  You can see why two monitors will be helpful if possible.

Zoom Access: password required - password is: idaho_geo

Topic: BCB 503 Geospatial Analysis Workshop

Join Zoom Meeting
https://uidaho.zoom.us/j/937557828?pwd=cFFndTM1QmltRGVaWmdIYU5FdWc1dz09

Meeting ID: 937 557 828

One tap mobile
+16699006833,,937557828# US (San Jose)
+16468769923,,937557828# US (New York)

Dial by your location
        +1 669 900 6833 US (San Jose)
        +1 646 876 9923 US (New York)
Meeting ID: 937 557 828
Find your local number: https://uidaho.zoom.us/u/aoetXY48n

Join by SIP
937557828@zoomcrc.com

Join by H.323
162.255.37.11 (US West)
162.255.36.11 (US East)
221.122.88.195 (China)
115.114.131.7 (India Mumbai)
115.114.115.7 (India Hyderabad)
213.19.144.110 (EMEA)
103.122.166.55 (Australia)
209.9.211.110 (Hong Kong)
64.211.144.160 (Brazil)
69.174.57.160 (Canada)
207.226.132.110 (Japan)
Meeting ID: 937 557 828
Password: 036740

