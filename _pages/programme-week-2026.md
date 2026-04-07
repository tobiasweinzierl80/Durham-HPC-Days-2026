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
  "10:30|Coffee Break,12:00|Lunch,14:30|Break,16:00|Coffee Break" | split: "," %}


{% for fs in fixed_sessions %}
  {% assign fs_parts = fs | split: "|" %}
  {% assign fs_time = fs_parts[0] %}
  {% assign fs_title = fs_parts[1] %}
  {% unless time_slots contains fs_time %}
    {% assign time_slots = time_slots | push: fs_time %}
  {% endunless %}
{% endfor %}

{% assign time_slots = time_slots | sort %}
<div class="mobile-programme-landing">
  <div class="mobile-landing-inner">
    <h1>Durham HPC Days 2026</h1>
    <p class="subtitle">Conference Programme - Mobile Version</p>
    <a href="/programme-days/" class="btn-see-programme">See Full Programme</a>
  </div>
</div>
<div class="programme-container">

<main class="programme-main">


<br> <br> 

<div class="programme-legend">

  <div class="legend-item keynote" data-category="keynote"><span class="legend-colour"></span> Keynotes</div>
  <div class="legend-item workshop" data-category="workshop"><span class="legend-colour"></span> Workshops</div>
  <div class="legend-item talk" data-category="talk"><span class="legend-colour"></span> Talks</div>
  <div class="legend-item tutorial" data-category="tutorial"><span class="legend-colour"></span> Tutorials</div>
  <div class="legend-item poster" data-category="poster"><span class="legend-colour"></span> Posters</div>
  <div class="legend-item social" data-category="social"><span class="legend-colour"></span> Socials</div>
  <div class="legend-item meeting" data-category="meeting"><span class="legend-colour"></span> Meetings</div>
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

    {% assign is_fixed = false %}
    {% assign fixed_title = "" %}

    {% for fs in fixed_sessions %}
      {% assign fs_parts = fs | split: "|" %}
      {% if fs_parts[0] == time %}
        {% assign is_fixed = true %}
        {% assign fixed_title = fs_parts[1] %}
      {% endif %}
    {% endfor %}

    {%- assign has_content = false -%}
    {% for day in days_order %}
      {% assign cell_sessions = all_sessions
        | where: "day", day
        | where: "start_time", time %}
      {% if cell_sessions.size > 0 %}
        {% assign has_content = true %}
      {% endif %}
    {% endfor %}

    {% if has_content or is_fixed %}

    <div class="week-row">

      <!-- Time column -->
      <div class="week-time">
        {% assign start_time = time | split: "-" | first %}
        {{ start_time }}
      </div>

      {% if is_fixed %}
        <div class="week-cell coffee" style="grid-column: span 5; text-align:center;">
          <h3>{{ fixed_title }}</h3>
        </div>

      {% else %}

        {% for day in days_order %}
          {% assign cell_sessions = all_sessions
            | where: "day", day
            | where: "start_time", time %}

          <div class="week-cell">
{% if cell_sessions.size == 0 %}
  <div class="week-cell empty-cell"></div>
{% else %}
              {% assign cell_sessions = cell_sessions | sort: "track" %}

              {% for s in cell_sessions %}
              <div class="session-card {{ s.category | downcase }}">
                <h3>
                  <a href="{{ s.url | relative_url }}">
                    {{ s.title }}
                  </a>
                </h3>

                {% if s.lead or s.instructor or s.facilitator %}
                <p class="speaker">

                  {% if s.lead %}
                    <strong>Lead{% if s.lead contains "," %}s{% endif %}:</strong>
                    {{ s.lead }}
                  {% endif %}

                  {% if s.lead and s.instructor %} · {% endif %}

                  {% if s.instructor %}
                    <strong>Instructor{% if s.instructor contains "," %}s{% endif %}:</strong>
                    {{ s.instructor }}
                  {% endif %}

                  {% if s.facilitator %}
                    <strong>Facilitator{% if s.facilitator contains "," %}s{% endif %}:</strong>
                    {{ s.facilitator }}
                  {% endif %}

                </p>
                {% endif %}

                {% if s.room %}
                  <p class="room">Room: {{ s.room }}</p>
                {% endif %}
              </div>
              {% endfor %}

            {% endif %}
          </div>
        {% endfor %}

      {% endif %}

    </div>

    {% endif %}

  {% endfor %}

</div>

</main>
</div>

<style>

/* === FULL WIDTH PAGE === */
.full-programme .page__inner-wrap,
.full-programme .page__content,
.page__inner-wrap,
.page__content {
  max-width: 100% !important;
  width: 100% !important;
  padding: 0 !important;
  margin: 0 !important;
}

.full-programme .page__content section {
  padding: 0 !important;
}

.programme-container {
  width: 100%;
  margin: 0;
  padding: 0;
  display: flex;
  position: relative;
}

.week-grid {
  display: grid;
  gap: 0.5rem;
}

.week-header,
.week-row {
  display: grid;
  grid-template-columns: 90px repeat(5, 1fr);
  gap: 0.5rem;
  align-items: stretch;
}

.week-day-header,
.week-time-header {
  font-weight: 700;
  text-align: center;
  background: #002A41;
  color: #fff;
  padding: 0.5rem;
  border-radius: 8px;
  font-size: 0.9rem;
}

.week-time {
  font-weight: 700;
  text-align: center;
  background: #f4f6f8;
  border-radius: 8px;
  padding: 0.5rem;
  font-size: 0.85rem;
}

.week-cell {
  background: #fff;
  border: 1px solid #dce3ec;
  border-radius: 8px;
  padding: 0.3rem;
  min-height: 40px;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.week-cell.empty-cell {
  background: #EEEEEE !important;
  border: none !important;
  box-shadow: none;
}

.session-card {
  margin-bottom: 0.3rem;
  padding: 0.4rem;
  border-left: 4px solid;
  border-radius: 6px;
  color: #002A41;
  flex-grow: 1;
  flex-shrink: 0;
  transition: background-color 0.2s ease, transform 0.15s ease, box-shadow 0.15s ease;
}

.session-card:last-child {
  margin-bottom: 0;
}

.session-card h3 {
  font-size: 0.7rem;
  margin: 0;
}

.session-card:hover {
  filter: brightness(1) saturate(1.4);
  transform: scale(1.03);
  box-shadow: 0 6px 16px rgba(0,0,0,0.25);
  cursor: pointer;
}

.session-card.dimmed {
  opacity: 0.15;
  transform: scale(0.98);
}

.session-card.highlighted {
  transform: scale(1);
  z-index: 5;
}

.session-card.opening {
  background-color: #68246D;
  color: #fff;
  border-left-color: #68246D;
}

.session-card.opening h3,
.session-card.opening .speaker,
.session-card.opening .room {
  color: #002A41;
}

.session-card.keynote {
  background-color: #f1e6f4;
  border-left-color: #68246d;
}

.session-card.meeting {
  background-color: #f8e4f0;
  border-left-color: #c85096;
}

.session-card.workshop {
  background-color: #e3eff9;
  border-left-color: #2975c1;
}

.session-card.talk {
  background-color: #e2f3ea;
  border-left-color: #00a86b;
}

.session-card.tutorial {
  background-color: #fff4cc;
  border-left-color: #f5b800;
}

.session-card.poster {
  background-color: #f8dada;
  border-left-color: #dc3232;
}

.session-card.social {
  background-color: #ffe8cc;
  border-left-color: #ff8c00;
  flex-grow: 0 !important;
  flex-shrink: 0;
}

.session-card.coffee {
  background-color: #f8fafc;
  border-left-color: #e2e8f0;
}

.week-cell:has(.session-card:not(.social)) .session-card.social {
  flex-grow: 0;
}

.session-card .speaker {
  font-size: 0.4rem;
  color: #333;
  margin: 0;
}

.session-card .room {
  font-size: 0.6rem;
  color: #444;
  margin: 0;
}

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
}

.week-cell.coffee h3 {
  margin: 0;
  font-size: 0.95rem;
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
    min-height: 40px;
  }

  .session-card h3 {
    font-size: 0.65rem;
  }
}
/* === LEGEND === */
.programme-legend {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
  margin: 0.5rem 3%;
  padding: 1rem 1.25rem;
  background: #f8fafc;
  border: 1px solid #e3e8ef;
  border-radius: 16px;
  box-shadow: 0 4px 18px rgba(0,0,0,0.04);
}

/* Legend pills */
.legend-item {
  display: flex;
  align-items: centre;
  gap: 0.6rem;
  padding: 0.5rem 0.9rem;
  font-size: 0.82rem;
  font-weight: 500;
  border-radius: 999px;
  background: #fff;
  border: 1px solid #e3e8ef;
  cursor: pointer;
  transition: all 0.2s ease;
}

.legend-item:hover {
  transform: translateY(-1px);
  box-shadow: 0 6px 18px rgba(0,0,0,0.08);
}

.legend-item.active {
  background: #002A41;
  color: #fff;
  border-color: #002A41;
  font-weight: 700;
}

/* Colour square */
.legend-colour {
  width: 18px;
  height: 18px;
  border-radius: 6px;
  border: 4px solid;
  flex-shrink: 0;
}

.legend-item.keynote .legend-colour {
  background-color: var(--keynote-bg);
  border-color: var(--keynote-border);
}

.legend-item.workshop .legend-colour {
  background-color: var(--workshop-bg);
  border-color: var(--workshop-border);
}

.legend-item.talk .legend-colour {
  background-color: var(--talk-bg);
  border-color: var(--talk-border);
}

.legend-item.tutorial .legend-colour {
  background-color: var(--tutorial-bg);
  border-color: var(--tutorial-border);
}

.legend-item.poster .legend-colour {
  background-color: var(--poster-bg);
  border-color: var(--poster-border);
}

.legend-item.social .legend-colour {
  background-color: var(--social-bg);
  border-color: var(--social-border);
}

.legend-item.meeting .legend-colour {
  background-color: var(--meeting-bg);
  border-color: var(--meeting-border);
}

/* Title */
.legend-title {
  width: 100%;
  text-align: centre;
  font-size: 0.6rem;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: #5f6c7b;
  font-weight: 600;
}




:root {
  --keynote-bg: #f1e6f4;
  --keynote-border: #68246d;

  --workshop-bg: #e3eff9;
  --workshop-border: #2975c1;

  --talk-bg: #e2f3ea;
  --talk-border: #00a86b;

  --tutorial-bg: #fff4cc;
  --tutorial-border: #f5b800;

  --poster-bg: #f8dada;
  --poster-border: #dc3232;

  --social-bg: #ffe8cc;
  --social-border: #ff8c00;

  --meeting-bg: #f8e4f0;
  --meeting-border: #c85096;
}



@media (max-width: 900px) {

 
  .programme-container {
    display: none !important;
  }

 
  .mobile-programme-landing {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    height: 100vh;
    background: linear-gradient(180deg, #f4f6f8, #ffffff);
    padding: 2rem 2rem;
    margin-top: 2rem;
  }

  .mobile-landing-inner h1 {
    font-size: 2rem;
    color: #002A41;
    margin-bottom: 0.5rem;
    font-weight: 700;
  }

  .mobile-landing-inner .subtitle {
    font-size: 1rem;
    color: #5f6c7b;
    margin-bottom: 2rem;
  }

  .mobile-landing-inner .btn-see-programme {
    display: inline-block;
    padding: 1rem 2rem;
    font-size: 1.1rem;
    font-weight: 700;
    color: #fff;
    background-color: #68246D;
    border-radius: 12px;
    text-decoration: none;
    transition: background-color 0.2s ease, transform 0.2s ease, box-shadow 0.2s ease;
  }

  .mobile-landing-inner .btn-see-programme:hover {
    background-color: #50205a;
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(0,0,0,0.15);
  }

}


@media (min-width: 901px) {
  .mobile-programme-landing {
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

document.addEventListener("click", function (event) {


  if (!activeCategory) return;

  const clickedInsideLegend = event.target.closest(".legend-item");


  if (!clickedInsideLegend) {
    activeCategory = null;

    legendItems.forEach(i => i.classList.remove("active"));
    resetHighlight();
  }

});
  legendItems.forEach(item => {

    const category = item.dataset.category;


    item.addEventListener("mouseenter", () => {
      if (!activeCategory) highlightCategory(category);
    });

    item.addEventListener("mouseleave", () => {
      if (!activeCategory) resetHighlight();
    });


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




