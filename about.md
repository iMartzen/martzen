---
layout: default
title: Over mij
---

<style>
.profile-header {
  display: flex;
  align-items: center;
  gap: 2em;
  margin: 2em 0;
  flex-wrap: wrap;
}

.profile-photo {
  flex-shrink: 0;
}

.profile-photo img {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  object-fit: cover;
  box-shadow: 0 4px 12px rgba(45, 27, 78, 0.3);
  border: 4px solid #6b4fc7;
}

.profile-intro {
  flex: 1;
  min-width: 300px;
}

.social-links {
  display: flex;
  gap: 1em;
  margin-top: 1em;
}

.social-links a {
  display: inline-flex;
  align-items: center;
  gap: 0.5em;
  padding: 0.5em 1em;
  background: linear-gradient(120deg, #6b4fc7, #8b6fd9);
  color: white;
  text-decoration: none;
  border-radius: 5px;
  transition: transform 0.2s, box-shadow 0.2s;
}

.social-links a:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(107, 79, 199, 0.3);
  color: white;
}

@media (max-width: 768px) {
  .profile-header {
    flex-direction: column;
    text-align: center;
  }
  
  .profile-photo img {
    width: 150px;
    height: 150px;
  }
}
</style>

<div class="profile-header">
  <div class="profile-photo">
    <img src="{{ '/assets/images/martzen.jpg' | relative_url }}" alt="Martzen Haagsma">
  </div>
  <div class="profile-intro">
    <h2>Hi, ik ben Martzen Haagsma 👋</h2>
    <p>Een tech professional die gelooft in de kracht van samenwerking. Mijn motto: <em>"Together we hit harder."</em></p>
    <div class="social-links">
      <a href="https://www.linkedin.com/in/martzen" target="_blank" rel="noopener noreferrer">
        <span>🔗</span> LinkedIn
      </a>
      <a href="https://github.com/iMartzen" target="_blank" rel="noopener noreferrer">
        <span>💻</span> GitHub
      </a>
    </div>
  </div>
</div>

---

### Wie ben ik?

Ik heb een honger naar kennis, ben leergierig en heb een onderzoekende geest. Ik denk graag in mogelijkheden in plaats van problemen. Door de jaren heen heb ik een uitgebreid netwerk opgebouwd waarmee ik de juiste persoon aan het juiste onderwerp kan koppelen. Als communicator, kritisch denker en oplossingsgericht professional werk ik graag samen om resultaten te bereiken.

### Wat doe ik?

Momenteel werk ik bij **HackerOne**, waar ik mijn ervaring in testing en security toepas, als Product Security Engineer. Mijn carrière heeft me door verschillende rollen gebracht:

- **HackerOne** - Huidige positie
- **ING** (2022-2024) – DevOps Engineer & IT Chapter Lead
- **Sogeti Nederland** (2017-2022) – Senior Agile Test Engineer
- **Ministerie van Economische Zaken en Klimaat** (2017-2018) – Security Tester  
- **Friesland College** (2012-2017) – Docent/coach

### Wat drijft mij?

- **Verbinden**: De juiste mensen aan de juiste uitdagingen koppelen
- **Communiceren**: Helder en effectief communiceren
- **Kritisch denken**: Altijd op zoek naar betere oplossingen
- **Samenwerken**: Samen komen we verder

---

_"Together we hit harder."_
