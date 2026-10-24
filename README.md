# The Habbache Hotel — AI Use Case

A single-page hotel website for **The Habbache Hotel**, a fictional London business hotel, built as a demonstration of IBM watsonx AI integration for an IU project.

---

## 🏨 About

The Habbache Hotel website showcases how an AI concierge (**Arria**) can be embedded into a hospitality website to handle bookings, answer guest queries, and provide 24/7 support — powered by **IBM Watson Assistant**.

---

## 🚀 Live Demo

Open `index.html` via a local HTTP server (see [Running Locally](#running-locally)) or deploy to any static hosting provider (GitHub Pages, Netlify, etc.).

---

## ✨ Features

- **Responsive single-page design** — hero, booking bar, rooms, amenities, testimonials, location & contact
- **Three room tiers** — Standard Business (£149/night), Executive Suite (£249/night), Penthouse Suite (£549/night)
- **Arria AI Concierge** — embedded IBM Watson Assistant chat widget for 24/7 guest support and bookings
- **Booking bar** — check-in/check-out date pickers, guest count, room type selector
- **Smooth scroll navigation** with sticky navbar
- **Pet-friendly amenity** section, testimonials, and Google Maps embed

---

## 🤖 AI Integration — IBM Watson Assistant

The chatbot widget is loaded via the Watson Assistant Web Chat embed:

```html
<script>
  window.watsonAssistantChatOptions = {
    integrationID: "9c52bcb0-e60d-4d72-be2e-7cee1152bf51",
    region: "https://integrations.eu-gb.assistant-builder.watson.appdomain.cloud",
    serviceInstanceID: "60fb0257-d377-4b16-940e-899fe9bd9b38",
    orchestrateUIAgentExtensions: false,
    onLoad: async (instance) => { await instance.render(); }
  };
  setTimeout(function(){
    const t = document.createElement('script');
    t.src = "https://web-chat.global.assistant.watson.appdomain.cloud/versions/" +
            (window.watsonAssistantChatOptions.clientVersion || 'latest') +
            "/WatsonAssistantChatEntry.js";
    document.head.appendChild(t);
  });
</script>
```

The `openArria()` helper is wired to all **"Book via Arria"** and **"Chat with Arria Now"** buttons on the page.

---

## 🛠 Running Locally

The Watson Assistant widget requires HTTP (not `file://`). Serve the project with:

```bash
python3 -m http.server 8080
```

Then open **http://localhost:8080** in your browser.

---

## 📁 Project Structure

```
.
└── index.html   # Full single-page website (HTML + CSS + JS, self-contained)
```

---

## 📞 Contact

- **Phone:** +44 7700 900123  
- **Email:** reservations@thehabbache.com  

---

## 🏗 Built With

- Plain HTML, CSS & JavaScript — no framework dependencies
- [IBM Watson Assistant](https://www.ibm.com/products/watson-assistant) — AI concierge (Arria)
- Built with **IBM Bob**
