---
layout: default
title: Register
permalink: /register/
---

<style>
.parallax-hero {
  width: 100vw;
  margin-left: calc(50% - 50vw);
  height: 50vh;
  background-image: url("https://github.com/hpc-days/Durham-HPC-Days-2026/blob/main/assets/images/eva-blue-banner-no-title.png?raw=true");
  background-attachment: fixed;
  background-position: 120% 80%;
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  align-items: center;
  justify-content: center;
}

.parallax-overlay {
  background: linear-gradient(rgba(104,36,109,0.85), rgba(70,20,75,0.85));
  color: white;
  padding: 2rem 15rem;
  text-align: center;
  border-radius: 14px;
  box-shadow: 0 15px 40px rgba(0,0,0,0.40);
}

.parallax-hero h1 {
  font-size: 4rem;
  margin-bottom: 0.5rem;
  color: white;
}

.parallax-hero p {
  font-size: 1.3rem;
  opacity: 0.95;
}

.price {
  font-size: 1.5rem;
  font-weight: 500;
  margin: 0.8rem 0 0.8rem;
  color: #002A41;
}
/* REGISTER CARD */
.card-highlight {
  background: white;
  padding: 2.5rem;
  border-left: 6px solid #68246D;
  border-radius: 12px;
  box-shadow: 0 12px 30px rgba(0,0,0,0.08);
  margin: 3rem auto;
  max-width: 1500px;
  width: 90%;
  text-align: center;
}

.card-highlight h2 {
  margin-bottom: 0.8rem;
}

.register-button {
  display: inline-block;
  margin-top: 1.5rem;
  padding: 0.9rem 2.2rem;
  background: #68246D;
  color: white !important;
  border-radius: 999px;
  text-decoration: none;
  font-weight: 600;
  font-size: 1rem;
  transition: background 0.2s ease, transform 0.2s ease;
}

.register-button:hover {
  background: #4e1a53;
  transform: scale(1.05);
}

.small-text {
  font-size: 0.85rem;
  color: #666;
  margin-top: 1rem;
}


/* CONTENT */
.section-register {
  max-width: 1200px;
  margin: auto;
  padding: 3rem 2rem;
}

.section-register h2 {
  margin-top: 1rem;
  font-size: 2rem;
}


/* CHECKLIST */
ul.checklist {
  list-style: none;
  padding: 0;
}

ul.checklist li {
  padding-left: 1.8rem;
  margin-bottom: 0.7rem;
  position: relative;
}

ul.checklist li::before {
  content: "✓";
  position: absolute;
  left: 0;
  color: #68246D;
  font-weight: bold;
}


/* INFO CENTRED BLOCK */
.info-centred {
  max-width: 720px;
  margin: 3rem auto;
  text-align: left;
}

.info-centred h2 {
  text-align: center;
}

.info-centred ul {
  padding-left: 1.2rem;
}



@media (max-width: 768px) {

  /* HERO */
  .parallax-hero {
    height: 32vh;
    min-height: 180px;
    background-attachment: scroll;
    background-position: center;
  }

  .parallax-hero h1 {
    font-size: 2.2rem;
    padding: 0 1rem;
    text-align: center;
  }

  .parallax-overlay {
    padding: 1.2rem 1.5rem;
    margin: 0 1rem;
    border-radius: 10px;
  }

  .parallax-hero p {
    font-size: 1rem;
  }

  /* MAIN SECTION */
  .section-register {
    padding: 1.8rem 1rem;
  }

  .section-register h2 {
    font-size: 1.5rem;
    line-height: 1.3;
  }

  /* CARD */
  .card-highlight {
    padding: 1.6rem 1.2rem;
    border-left: 4px solid #68246D;
    border-radius: 10px;
    width: 100%;
    margin: 1.5rem auto;
  }

  .card-highlight p {
    font-size: 0.95rem;
    line-height: 1.6;
  }

  /* PRICE */
  .price {
    font-size: 1.2rem;
    margin: 0.6rem 0 0.8rem;
  }

  /* BUTTON */
  .register-button {
    width: 100%;
    max-width: 320px;
    margin: 1.2rem auto 0;
    display: block;
    text-align: center;
    padding: 0.85rem 1.4rem;
    font-size: 0.95rem;
  }

  .register-button:hover {
    transform: none; /* avoid weird zoom on mobile */
  }

  /* SMALL TEXT */
  .small-text {
    font-size: 0.8rem;
    line-height: 1.4;
  }

  /* INFO BLOCKS */
  .info-centred {
    margin: 2rem auto;
    padding: 0 0.5rem;
  }

  .info-centred h2 {
    font-size: 1.4rem;
    margin-bottom: 0.6rem;
  }

  .info-centred ul {
    padding-left: 1rem;
  }

  .info-centred li {
    font-size: 0.95rem;
    margin-bottom: 0.5rem;
  }

  /* CHECKLIST */
  ul.checklist li {
    padding-left: 1.5rem;
    font-size: 0.95rem;
  }

  /* TRAVEL / ACCOMMODATION TEXT FIX */
  .info-centred ul br {
    display: none; /* remove messy line breaks */
  }

}

</style>


<section class="parallax-hero">
    <h1>Register</h1>
</section>


<section class="section-register">
  <div class="card-highlight">
    <h2>Registration closes on 20 April</h2>
    <p>
      Secure your place at <strong>Durham HPC Days 2026</strong>, a leading UK event
      in High Performance Computing, hosted at Durham University.
    </p>
<p class="price">
  🎟️ Registration fee: <strong>£50</strong>
</p>
      

    <a class="register-button"
       href="https://pay.durham.ac.uk/event-durham/durham-hpc-days-2026"
       target="_blank" rel="noopener">
       Register Now
    </a>

    <p class="small-text">
      You will be redirected to the official Durham University registration system.
    </p>
    
        <p class="small-text">
      Lunch and light dinners will be provided to all registered attendees throughout the conference week. These meals are kindly subsidised by our sponsors.
    </p>
    
  </div>

<div class="info-centred">

  <h2>Why attend?</h2>
  <ul class="checklist">
    <li>Keynotes by leading HPC researchers and practitioners</li>
    <li>Hands-on sessions and tutorials </li>
    <li>Networking with industry and academic experts</li>
    <li>Insights into modern HPC infrastructure and workflows</li>
    <li>Opportunities for collaboration and knowledge exchange</li>
  </ul>


  <h2>Important information</h2>
  <ul>
    <li>Places are limited — early registration is strongly recommended.</li>
    <li>Please get in touch if you have any questions.</li>
  </ul>
 </div>
 
 <div class="info-centred">
   <h2>Travel</h2>
  <ul>
  The University’s official <a href= "https://www.durham.ac.uk/visit-us/" > Visit Us</a>  page provides some general guidance. Here are some further remarks how to get there: <br> <br>
  
    <li>If you are arriving at Newcastle International, take the tram (there’s only one) to Newastle Central (less than 40 minute) and then take a train to the South. Durham is 15 minutes away from Newcastle Central</li>
    <li>Alternatively, you can take a taxi from the airport (should be around 60 GBP for a drive of around 40 minutes in total).</li>
        <li>From Durham train station, it is a 30-40 minute walk.</li>
        <li>Taxis should be available from the station and should be around 10-15 GBP. </li>
        <li> Right in front of the station, there’s a bus stop with two lines </li>
  </ul>
    <ul class="checklist">
    <li>Bus 42 to Mount Oswald. It runs every 30 minutes. Get off at “South Road Colleges” and walk up the hill from there (5 minutes).</li>
    <li>Bus 41 to University Science Park. Hop off at the final stop.</li>
  </ul>
  
  <div class="info-centred">
   <h2>Accommodation</h2>
  <ul>
  There is no financial or logistics support for accommodation and travel, but we can point to a few hotels nearby that guests of the department use frequently. Participants will need to make all booking:<br> <br>
  <li> <a href= "https://durham.hotelindigo.com/" > Hotel Indigo </a> </li>
    <li> <a href= "https://www.premierinn.com/gb/en/hotels/england/county-durham/durham/durham-city-centre-walkergate.html" > Premier Inn </a> </li>
 <li> <a href= "https://www.guestreservations.com/marriott-durham/booking?utm_source=google&utm_medium=cpc&utm_campaign=991006015&gad_source=1&gad_campaignid=991006015&gclid=CjwKCAiA7LzLBhAgEiwAjMWzCFawpcLQS7qO2pY_GdW2jqAGlVOc8rSwmJVPjCG0iUOj0IbzaN-gYhoCfasQAvD_BwE" > Marriott </a> </li>
  <li> <a href= "https://www.travelodge.co.uk/hotels/204/Durham-hotel" > Travelodge </a> </li>
  
The University has their own <a href= "https://www.durham.ac.uk/event-durham/" > Events team </a>. They also provide B&B accommodation. However, as we approach the new term, it is not likely that they have “spare” rooms.
    



