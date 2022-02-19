---
layout: page
title: events
permalink: /calendar/
description: Calgary AI Upcoming Events
nav: true
nav-order: 3
---
<!-- <script src="https://cdn.jsdelivr.net/npm/@fullcalendar/core@5/main.min.js" referrerpolicy="no-referrer"></script>
<script src="https://cdn.jsdelivr.net/npm/@fullcalendar/daygrid@5/main.js" referrerpolicy="no-referrer"></script>
<script src="https://cdn.jsdelivr.net/npm/@fullcalendar/icalendar@5/main.js" referrerpolicy="no-referrer"></script>
<script src="https://cdn.jsdelivr.net/npm/@fullcalendar/interaction@5/main.js" referrerpolicy="no-referrer"></script> -->
<!-- <script src="https://cdn.jsdelivr.net/npm/fullcalendar@5/main.min.js"></script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/fullcalendar@5.10.2/main.min.css"> -->

<link href="https://cdn.jsdelivr.net/npm/fullcalendar@5.5.1/main.min.css" rel="stylesheet" />
<script src="https://cdnjs.cloudflare.com/ajax/libs/ical.js/1.5.0/ical.min.js" integrity="sha512-0izBc1upGYnrS1u1MX7QR+sjFIxZWxLVdNI7cUoHHCutDr5ENjuQRZuS+v+3NFNGfwHSrPoHzBzED0rV651tGw==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
<script src="https://cdn.jsdelivr.net/npm/fullcalendar@5.5.1/main.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/fullcalendar@5.5.1/locales-all.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@fullcalendar/icalendar@5.5.1/main.global.min.js"></script>

<script>
document.addEventListener("DOMContentLoaded", function () {
  var calendarEl = document.getElementById("calendar");

  var calendar = new FullCalendar.Calendar(calendarEl, {
    initialView: "dayGridMonth",
    headerToolbar: {
      left: "prev,next today",
      center: "title",
      right: "dayGridMonth,timeGridWeek,timeGridDay",
    },
    // plugins: [DayGridPlugin, iCalendarPlugin],
    events: {
      url: "https://calendar.google.com/calendar/ical/0h136a1ol57kjhjm5oqm0kibao%40group.calendar.google.com/public/basic.ics",
      format: "ics",
    },
  });

  calendar.render();
});
</script>
<div id='calendar'></div>