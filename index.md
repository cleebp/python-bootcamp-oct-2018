---
layout: workshop      # DON'T CHANGE THIS.
carpentry: "swc"    # what kind of Carpentry (must be either "lc" or "dc" or "swc")
venue: "AI Python Bootcamp"        # brief name of host site without address (e.g., "Euphoric State University")
address: "Room 1"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "us"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
latlng: "35.991550,-78.902750"       # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use https://www.latlong.net/)
humandate: "Tuesday Oct. 9th"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:00 am - 3:00 pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2018-10-09      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2018-10-09        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Brian Clee"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["_dan_salo, _joe_peck"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["bclee@automatedinsights.com"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes: https://docs.google.com/document/d/1m3_nEheECQHdVsu_kHMSrVLrZpfaSzxEux64SRU5SaM/edit?usp=sharing  # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document\
---

<h4>Welcome to the landing page for AI's Python Bootcamp. Here you will find schedule and setup info. The workshop files are hosted on Google Drive
<a href="https://drive.google.com/drive/folders/1eh2PH9Wd-lsLHEfaenHtlsNw9MFXqeUa?usp=sharing">here</a>, please Download
the entire `swc-python` folder and place in your development directory, we will be working out of its root. A shared google doc is located
<a href="https://docs.google.com/document/d/1m3_nEheECQHdVsu_kHMSrVLrZpfaSzxEux64SRU5SaM/edit?usp=sharing">here</a> for collaborative notetaking.</h4>

<h2 id="general">General Information</h2>

{% comment %}
  AUDIENCE
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/who.html %}
{% endif %}

{% comment %}
  LOCATION
{% endcomment %}
<strong>Where:</strong>
  Room 1.

{% comment %}
  DATE

  This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
</p>
{% endif %}

{% comment %}
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring their mac laptop with a
  text editor of choice installed. They should have Python 3.6.6 installed (listed
  <a href="#setup">below</a>).
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
<h2 id="surveys">Survey</h2>
<p>Please be sure to complete this survey after the workshop (LINK WILL BE POSTED SOON).</p>

<hr/>


{% comment %}
  SCHEDULE

  Show the workshop's schedule.  Edit the items and times in the table
  to match your plans.  You may also want to change 'Day 1' and 'Day
  2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule & Syllabus</h2>

{% if page.carpentry == "swc" %}
  {% include sc/schedule.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/schedule.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/schedule.html %}
{% endif %}

{% comment %}
  Collaborative Notes
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>

<h2 id="setup">Setup</h2>

<div id="python"> {% comment %} Start of 'Python' section. Remove the third paragraph if
           the workshop will teach Python using something other than
           the Jupyter notebook.
           Details at https://jupyter-notebook.readthedocs.io/en/stable/notebook.html#browser-compatibility {% endcomment %}
  <h3>Python</h3>

  <p>
    Regardless of how you choose to install it,
    <strong>please make sure you install Python version 3.x</strong>
    (e.g., 3.6 is fine).
  </p>

  <p>
    I reccommend directly installing Python 3.6.6 to your system root, this will give you the most control over your python configuration.
    You can install the files from the bottom of <a href="https://www.python.org/downloads/release/python-366/">this page</a>.
    Alternatively you can install the <a href="https://www.anaconda.com/distribution/">Anaconda</a>,
    all-in-one installer - a mores streamlined system setup that will require less configuration but give you less control.
  </p>
</div> {% comment %} End of 'Python' section. {% endcomment %}
