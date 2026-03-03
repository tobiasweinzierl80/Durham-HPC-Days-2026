---
layout: splash
title: "Conference Programme – Week View"
permalink: /programme-week-2026/
classes: [full-programme]
---

{% assign all_sessions = site.programme-days-2026
  | where_exp: "s", "s.start_time"
  | sort: "start_time" %}



{% assign tracks = "A,B,C,D" | split: "," %}
{% assign days_order = "Monday,Tuesday,Wednesday,Thursday,Friday" | split: "," %}
{% assign time_slots = all_sessions | map: "start_time" | uniq | sort %}

{% assign fixed_sessions = 
  "10:30|Coffee Break,12:00|Lunch,16:00|Coffee Break" | split: "," %}


{% for fs in fixed_sessions %}
  {% assign fs_parts = fs | split: "|" %}
  {% assign fs_time = fs_parts[0] %}
  {% assign fs_title = fs_parts[1] %}
  {% unless time_slots contains fs_time %}
    {% assign time_slots = time_slots | push: fs_time %}
  {% endunless %}
{% endfor %}

{% assign time_slots = time_slots | sort %}

<div class="programme-container">

<main class="programme-main">
<br> <br> 
  <h1 style="margin-left:3%"> Weekly Programme Overview</h1>
 
<div class="programme-legend">
<h3 class="legend-title">Filter by session type</h3>
  <div class="legend-item keynote" data-category="keynote">
    <span class="legend-colour"></span> Keynotes
  </div>

  <div class="legend-item workshop" data-category="workshop">
    <span class="legend-colour"></span> Workshops
  </div>

  <div class="legend-item talk" data-category="talk">
    <span class="legend-colour"></span> Talks
  </div>

  <div class="legend-item tutorial" data-category="tutorial">
    <span class="legend-colour"></span> Tutorials
  </div>

  <div class="legend-item poster" data-category="poster">
    <span class="legend-colour"></span> Posters
  </div>

  <div class="legend-item social" data-category="social">
    <span class="legend-colour"></span> Socials
  </div>
  
    <div class="legend-item meeting" data-category="meeting">
    <span class="legend-colour"></span> Meetings
  </div>

</div>
  <div class="week-grid">




    <!-- Header -->
    <div class="week-header">
      <div class="week-time-header">Time</div>
      {% for day in days_order %}
        <div class="week-day-header">{{ day }}</div>
      {% endfor %}
    </div>

    <!-- Rows by time -->
  {% for time in time_slots %}
  <div class="week-row">

    <!-- Time column -->
    <!-- Time column -->
<div class="week-time">
  {% assign start_time = time | split: "-" | first %}
  {{ start_time }}
</div>

    {% assign is_fixed = false %}
    {% assign fixed_title = "" %}
    {% for fs in fixed_sessions %}
      {% assign fs_parts = fs | split: "|" %}
      {% if fs_parts[0] == time %}
        {% assign is_fixed = true %}
        {% assign fixed_title = fs_parts[1] %}
      {% endif %}
    {% endfor %}

    {% if is_fixed %}
      <div class="week-cell coffee" style="grid-column: span 5; text-align:center;">
        <h3>{{ fixed_title }}</h3>
      </div>
    {% else %}
      <!-- Bucle normal por días -->
      {% for day in days_order %}
        {% assign cell_sessions = all_sessions
          | where: "day", day
          | where: "start_time", time %}

        <div class="week-cell">
          {% if cell_sessions.size == 0 %}
            <span class="empty">–</span>
          {% else %}
          {% assign cell_sessions = cell_sessions | sort: "track" %}

{% for s in cell_sessions %}
  <div class="session-card {{ s.category | downcase }}">
    <h3>
      <a href="{{ s.url | relative_url }}">
        {% if s.track %}{% endif %}
        {{ s.title }}
      </a>
    </h3>
{% if s.lead or s.instructor or s.facilitator %}
  <p class="speaker">

    {% if s.lead %}
      <strong>
        Lead{% if s.lead contains "," %}s{% endif %}:
      </strong>
      {{ s.lead }}
    {% endif %}

    {% if s.lead and s.instructor %} · {% endif %}

    {% if s.instructor %}
      <strong>
        Instructor{% if s.instructor contains "," %}s{% endif %}:
      </strong>
      {{ s.instructor }}
    {% endif %}
    
      {% if s.facilitator %}
      <strong>
        Facilitator{% if s.facilitator contains "," %}s{% endif %}:
      </strong>
      {{ s.facilitator }}
    {% endif %}

  </p>
{% endif %}

    {% if s.room %}<p class="room">Room: {{ s.room }}</p>{% endif %}
  </div>
{% endfor %}

          {% endif %}
        </div>
      {% endfor %}
    {% endif %}

  </div>
{% endfor %}



  </div>




</main>
</div>

<style>


.full-programme .page__inner-wrap,
.full-programme .page__content,
.page__inner-wrap,
.page__content {
  max-width: 100% !important;
  width: 100% !important;
  padding-left: 0 !important;
  padding-right: 0 !important;
  margin-left: 0 !important;
  margin-right: 0 !important;
}


.full-programme .page__content section {
  padding-left: 0 !important;
  padding-right: 0 !important;
}

.programme-container {
  width: 100%;
  padding: 0 !important;
  margin: 0 !important;
}

.session-card.coffee {
  background-color: #F8FAFC; 
  border-left-color: #F8FAFC;
}

.session-card.coffee h3 a {
  color: #002A41 !important;
  text-align: center;
}


/* Layout */
.programme-container {
  width: 100%;
  max-width: 100% !important;
  padding: 0;    
  margin: 0;  
}

/* Weekly grid */
.week-grid {
  display: grid;
  gap: 0.5rem;
}

/* Header + rows */
.week-header,
.week-row {
  display: grid;
  grid-template-columns: 90px repeat(5, 1fr);
  gap: 0.5rem;
}

/* Headers */
.week-day-header {
  font-weight: 700;
  text-align: center;
  background: #002A41;
  color: #ffffff;
  padding: 0.5rem;
  border-radius: 8px;
  font-size: 0.9rem;
}

.week-time-header {
  font-weight: 700;
  text-align: center;
  background: #002A41;
  color: #ffffff;
  padding: 0.5rem;
  border-radius: 8px;
  font-size: 0.9rem;
}

/* Time column */
.week-time {
  font-weight: 700;
  text-align: center;
  background: #f4f6f8;
  border-radius: 8px;
  padding: 0.5rem;
  font-size: 0.85rem;
}

/* Cells */
.week-cell {
  background: #ffffff;
  border: 1px solid #dce3ec;
  border-radius: 8px;
  padding: 0.3rem;
  min-height: 90px;
}

/* Empty cells */
.week-cell .empty {
  display: block;
  text-align: center;
  color: #ccc;
}

/* Session cards */
.week-cell .session-card {
  margin-bottom: 0.3rem;
  padding: 0.4rem;
  border-left: 4px solid;
  border-radius: 6px;
  color: #002A41;
}

.week-cell .session-card h3 {
  font-size: 0.7rem;
  margin: 0;
  color: #002A41 !important;
}


.programme-legend {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
  margin: 2rem 3%;
  padding: 1rem 1.25rem;
  background: #f8fafc;
  border: 1px solid #e3e8ef;
  border-radius: 16px;
  align-items: center;
  box-shadow: 0 4px 18px rgba(0,0,0,0.04);

  align-items: flex-start;
}



/* Each legend item becomes a pill */
.legend-item {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  padding: 0.5rem 0.9rem;
  font-size: 0.82rem;
  font-weight: 500;
  border-radius: 999px;
  background: #ffffff;
  border: 1px solid #e3e8ef;
  cursor: pointer;
  transition: 
    all 0.2s ease,
    transform 0.15s ease;
}

/* Hover */
.legend-item:hover {
  transform: translateY(-1px);
  box-shadow: 0 6px 18px rgba(0,0,0,0.08);
}

/* Active state */
.legend-item.active {
  background: #002A41;
  color: #ffffff;
  border-color: #002A41;
}

/* Colour square */
.legend-colour {
  width: 18px;
  height: 18px;
  border-radius: 6px;
  border: 4px solid;
  flex-shrink: 0;
}

/* When active → colour square becomes lighter for contrast */
.legend-item.active .legend-colour {
  filter: brightness(1.1);
}
.legend-title {
  margin-top: 0.7rem;
  font-size: 0.6rem;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: #5f6c7b;
  font-weight: 600;
  width: 100%;

  display: flex;
  justify-content: center;   /* horizontal center */
}
}

.legend-item.opening .legend-colour {
  background-color: #68246D;
  border-color: #68246D;
}

.legend-item.keynote .legend-colour {
  background-color: #DFDBF5;
  border-color: #78206E;
}

.legend-item.meeting .legend-colour {
  background-color: #F5DBF2;
  border-color: #2E2278;
}

.legend-item.workshop .legend-colour {
  background-color: #D3E4F5;
  border-color: #194775;
}

.legend-item.talk .legend-colour {
  background-color: #D1E5D2;
  border-color: #315933;
}

.legend-item.session .legend-colour {
  background-color: #F3E5F5;
  border-color: #9C27B0;
}

.legend-item.tutorial .legend-colour {
  background-color: #E6DDC0;
  border-color: #534721;
}

.legend-item.poster .legend-colour {
  background-color: #CEBCBC;
  border-color: #7A5958;
}

.legend-item.coffee .legend-colour {
  background-color: #F8FAFC;
  border-color: #F8FAFC;
}

.legend-item.social .legend-colour {
  background-color: #F8FAFC;
  border-color: #F8FAFC;
}


.session-card.dimmed {
  opacity: 0.15;
  transform: scale(0.98);
}

.session-card.highlighted {
  box-shadow: 0 0 0 0px rgba(0,42,65,0.6);
  transform: scale(1.00);
  z-index: 5;
}

.legend-item {
  cursor: pointer;
  transition: transform 0.15s ease, opacity 0.15s ease;
}

.legend-item:hover {
  transform: scale(1.0);
}

.legend-item.active {
  font-weight: 700;
}


.session-card.opening { background-color: #68246D; color: #fff; border-left-color: #68246D; }
.session-card.opening h3, .session-card.opening .speaker, .session-card.opening .room { color: #002A41; }



.session-card.keynote { background-color: #DFDBF5; border-left-color: #2E2278; }
.session-card.meeting { background-color: #F5DBF2; border-left-color: #78206E; }
.session-card.workshop { background-color: #D3E4F5; border-left-color: #194775; }
.session-card.talk { background-color: #D1E5D2; border-left-color: #315933; }
.session-card.session { background-color: #F3E5F5; border-left-color: #9C27B0; }
.session-card.tutorial { background-color: #E6DDC0; border-left-color: #534721; }
.session-card.poster { background-color: #CEBCBC; border-left-color: #7A5958; }
.session-card.coffee { background-color: #F8FAFC; border-left-color: #F8FAFC; }
.session-card.social { background-color: #F8FAFC; border-left-color: #F8FAFC; }

.session-card .speaker { font-size: 0.4rem; color: #333; margin:0; }
.session-card .room { font-size: 0.6rem; color: #444; margin:0; }

.week-cell .session-card h3 a {
  color: inherit !important;
}
.session-card.opening h3 a {
  color: #ffffff !important;
}

.session-card.workshop h3 a,
.session-card.talk h3 a,
.session-card.session h3 a,
.session-card.tutorial h3 a,
.session-card.poster h3 a,

.session-card.social h3 a {
  color: #002A41 !important;
}

.week-cell.coffee {
  display: flex;
  align-items: center;  
  justify-content: center;
  padding: 0.3rem;  
  min-height: 70px;
  margin-top: 0; 
}

.week-cell.coffee h3 {
  margin: 0; 
  font-size: 0.95rem;
}


.week-cell .session-card {
  transition: 
    background-color 0.2s ease,
    transform 0.15s ease,
    box-shadow 0.15s ease;
}

.week-cell .session-card:hover {
  filter: brightness(1) saturate(1.4);
  transform: scale(1.03);
  box-shadow: 0 6px 16px rgba(0,0,0,0.25);
  cursor: pointer;
}

.week-grid::-webkit-scrollbar {
  height: 6px;
}

.week-grid::-webkit-scrollbar-thumb {
  background: #cbd5e1;
  border-radius: 999px;
}

@media (max-width: 900px) {

  .week-grid {
    overflow-x: auto;
    padding-bottom: 0.5rem;
  }

  .week-header,
  .week-row {
    grid-template-columns: 70px repeat(5, minmax(220px, 1fr));
  }

  .week-day-header,
  .week-time-header {
    font-size: 0.75rem;
  }

  .week-cell {
    min-height: 70px;
  }

  .session-card h3 {
    font-size: 0.65rem;
  }
  
  .programme-legend {
   display: none;
  }

}

</style>


<script>
document.addEventListener("DOMContentLoaded", function () {

  const legendItems = document.querySelectorAll(".legend-item");
  const sessions = document.querySelectorAll(".session-card");

  let activeCategory = null;

  function highlightCategory(category) {
    sessions.forEach(session => {
      if (session.classList.contains(category)) {
        session.classList.add("highlighted");
        session.classList.remove("dimmed");
      } else {
        session.classList.add("dimmed");
        session.classList.remove("highlighted");
      }
    });
  }

  function resetHighlight() {
    sessions.forEach(session => {
      session.classList.remove("highlighted", "dimmed");
    });
  }
// Click outside legend resets everything
document.addEventListener("click", function (event) {

  // If no active filter, do nothing
  if (!activeCategory) return;

  const clickedInsideLegend = event.target.closest(".legend-item");

  // If click is NOT inside legend, reset
  if (!clickedInsideLegend) {
    activeCategory = null;

    legendItems.forEach(i => i.classList.remove("active"));
    resetHighlight();
  }

});
  legendItems.forEach(item => {

    const category = item.dataset.category;

    // Hover effect (only if nothing locked)
    item.addEventListener("mouseenter", () => {
      if (!activeCategory) highlightCategory(category);
    });

    item.addEventListener("mouseleave", () => {
      if (!activeCategory) resetHighlight();
    });

    // Click to lock
    item.addEventListener("click", () => {

      if (activeCategory === category) {
        // Clicking again resets
        activeCategory = null;
        item.classList.remove("active");
        resetHighlight();
      } else {
        activeCategory = category;

        legendItems.forEach(i => i.classList.remove("active"));
        item.classList.add("active");

        highlightCategory(category);
      }

    });

  });

});
</script>

