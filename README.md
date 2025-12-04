# Guide Complet - Arbre Généalogique Option 2 (Structurée)

## 📋 Structure finale

```
mon-arbre-genealogique/
├── index.html
├── README.md
├── CONTRIBUER.md
├── families/
│   ├── rossi-bianchi/
│   │   ├── data.json
│   │   ├── rossi_marco/
│   │   │   ├── info.txt
│   │   │   ├── photo1.jpg           # Image 1 (max 5 images)
│   │   │   ├── photo2.jpg           # Image 2
│   │   │   ├── photo3.jpg           # Image 3
│   │   │   └── ...
│   │   ├── bianchi_anna/
│   │   │   ├── info.txt
│   │   │   ├── photo1.jpg
│   │   │   └── photo2.jpg
│   │   ├── rossi_luca/
│   │   │   ├── info.txt
│   │   │   └── photo1.jpg
│   │   └── ...
│   └── verdi-ferrari/
│       ├── data.json
│       └── ...
└── docs/
    ├── FORMAT.md
    └── EXAMPLES.md
```

---

## 🔧 Étape 1: Créer le repo sur GitHub

1. Va sur [github.com](https://github.com)
2. Clique sur **"New repository"**
3. Nomme-le: `mon-arbre-genealogique`
4. Cocher: "Add a README file"
5. Clique **"Create repository"**

---

## 💻 Étape 2: Cloner le repo

```bash
git clone https://github.com/TONUSERNAME/mon-arbre-genealogique.git
cd mon-arbre-genealogique
```

---

## 📁 Étape 3: Créer la structure

```bash
mkdir -p families/rossi-bianchi/{rossi_marco,bianchi_anna,rossi_luca,rossi_clara,rossi_matteo,rossi_giulia}
mkdir -p families/verdi-ferrari/{verdi_carlo,ferrari_rosa}
mkdir docs
```

**OU manuellement** (pour ceux qui n'aiment pas le terminal):
- Crée dossier `families/`
  - Crée dossier `rossi-bianchi/`
    - Crée dossier `rossi_marco/` et ajoute `info.txt` + `photo.jpg`
    - Crée dossier `bianchi_anna/` et ajoute `info.txt` + `photo.jpg`
    - Etc.
  - Crée dossier `verdi-ferrari/`
    - Etc.

---

## 📄 Étape 4: Créer `families/rossi-bianchi/data.json`

```json
{
  "rossi_marco": {
    "id": "rossi_marco",
    "name": "Marco Rossi",
    "birth": "15-01-1950",
    "death": "22-03-2010",
    "birthPlace": "Roma",
    "profession": "Ingegnere",
    "images": [
      "families/rossi-bianchi/rossi_marco/photo1.jpg"
    ],
    "notes": "Fondatore dell'azienda",
    "parents": null,
    "partners": [
      {
        "id": "bianchi_anna",
        "children": ["rossi_luca", "rossi_giulia"]
      }
    ]
  },
  "rossi_luca": {
    "id": "rossi_luca",
    "name": "Luca Rossi",
    "birth": "12-03-1975",
    "death": null,
    "birthPlace": "Roma",
    "profession": "Medico",
    "images": [
      "families/rossi-bianchi/rossi_luca/photo1.jpg"
    ],
    "notes": "Lavora all'ospedale",
    "parents": ["rossi_marco", "bianchi_anna"],
    "partners": [
      {
        "id": "rossi_clara",
        "children": ["rossi_matteo"]
      },
      {
        "id": "rossi_sofia",
        "children": ["rossi_anna"]
      }
    ]
  },
  "bianchi_anna": {
    "id": "bianchi_anna",
    "name": "Anna Bianchi",
    "birth": "08-06-1952",
    "death": null,
    "birthPlace": "Milano",
    "profession": "Insegnante",
    "image": "families/rossi-bianchi/bianchi_anna/photo.jpg",
    "notes": "Dedita alla famiglia",
    "parents": null,
    "partner": "rossi_marco",
    "children": ["rossi_luca", "rossi_giulia"]
  },
  "rossi_luca": {
    "id": "rossi_luca",
    "name": "Luca Rossi",
    "birth": "12-03-1975",
    "death": null,
    "birthPlace": "Roma",
    "profession": "Medico",
    "image": "families/rossi-bianchi/rossi_luca/photo.jpg",
    "notes": "Lavora all'ospedale",
    "parents": ["rossi_marco", "bianchi_anna"],
    "partner": "rossi_clara",
    "children": ["rossi_matteo"]
  },
  "rossi_clara": {
    "id": "rossi_clara",
    "name": "Clara Rossi",
    "birth": "20-05-1976",
    "death": null,
    "birthPlace": "Firenze",
    "profession": "Architetto",
    "image": "families/rossi-bianchi/rossi_clara/photo.jpg",
    "notes": null,
    "parents": null,
    "partner": "rossi_luca",
    "children": ["rossi_matteo"]
  },
  "rossi_matteo": {
    "id": "rossi_matteo",
    "name": "Matteo Rossi",
    "birth": "03-07-2000",
    "death": null,
    "birthPlace": "Roma",
    "profession": null,
    "image": "families/rossi-bianchi/rossi_matteo/photo.jpg",
    "notes": "Studente",
    "parents": ["rossi_luca", "rossi_clara"],
    "partner": null,
    "children": []
  },
  "rossi_giulia": {
    "id": "rossi_giulia",
    "name": "Giulia Rossi",
    "birth": "20-09-1978",
    "death": null,
    "birthPlace": "Roma",
    "profession": "Avvocata",
    "image": "families/rossi-bianchi/rossi_giulia/photo.jpg",
    "notes": "Partner in studio legale",
    "parents": ["rossi_marco", "bianchi_anna"],
    "partner": null,
    "children": []
  }
}
```

---

## 📝 Étape 5: Créer les `info.txt` pour chaque personne

**Exemple: `families/rossi-bianchi/rossi_marco/info.txt`**

```
Nome: Marco Rossi
Nato: 15-01-1950
Morto: 22-03-2010
Luogo di nascita: Roma
Professione: Ingegnere
Note: Fondatore dell'azienda

Famiglia:
- Partner: Anna Bianchi
- Figli: Luca Rossi, Giulia Rossi
```

**Fais la même chose pour chaque personne** dans leur dossier respectif.

---

## 🖼️ Étape 6: Ajouter les photos

Pour chaque personne:

1. Va dans son dossier: `families/rossi-bianchi/rossi_marco/`
2. Ajoute une photo: `photo.jpg` (ou `.png`)

**Important**: Le fichier DOIT s'appeler `photo.jpg` exactement!

Si tu n'as pas de photo, mets `"image": null` dans le JSON.

---

## 📄 Étape 7: Créer `families/verdi-ferrari/data.json`

Fais la même chose pour les autres familles:

```json
{
  "verdi_carlo": {
    "id": "verdi_carlo",
    "name": "Carlo Verdi",
    "birth": "03-05-1945",
    "death": "18-11-2005",
    "birthPlace": "Torino",
    "profession": "Commerciante",
    "image": "families/verdi-ferrari/verdi_carlo/photo.jpg",
    "notes": null,
    "parents": null,
    "partner": "ferrari_rosa",
    "children": []
  },
  "ferrari_rosa": {
    "id": "ferrari_rosa",
    "name": "Rosa Ferrari",
    "birth": "14-07-1948",
    "death": null,
    "birthPlace": "Firenze",
    "profession": "Casalinga",
    "image": "families/verdi-ferrari/ferrari_rosa/photo.jpg",
    "notes": null,
    "parents": null,
    "partner": "verdi_carlo",
    "children": []
  }
}
```

---

## 🔗 Étape 8: Modifier `index.html`

**À REMPLACER** (vers la fin du `<script>`):

```javascript
const familyData = {
    "rossi_marco": { ... },
    ...
};
```

**PAR CECI:**

```javascript
let familyData = {};
let families = [];

async function loadFamilies() {
    try {
        // Charger la liste des familles
        const familiesConfig = [
            'families/rossi-bianchi/data.json',
            'families/verdi-ferrari/data.json'
            // Ajoute d'autres familles ici si besoin
        ];

        // Charger chaque fichier JSON
        for (const familyFile of familiesConfig) {
            const response = await fetch(familyFile);
            const data = await response.json();
            Object.assign(familyData, data);
        }

        console.log('Données chargées:', Object.keys(familyData).length, 'personnes');
        resizeCanvas();
    } catch (error) {
        console.error('Erreur chargement données:', error);
    }
}

// Charger les données au démarrage
loadFamilies();
```

**AUSSI** change cette ligne à la fin:

```javascript
// Init
resizeCanvas();
window.addEventListener('resize', resizeCanvas);
```

EN:

```javascript
// Init
// resizeCanvas(); // Maintenant appelé par loadFamilies()
window.addEventListener('resize', resizeCanvas);
```

---

## 📖 Étape 9: Créer `README.md`

```markdown
# Arbre Généalogique Famille Rossi

Explorez l'histoire de notre famille avec cet arbre généalogique interactif!

## 🌳 Voir l'arbre

[Cliquez ici pour voir l'arbre généalogique](https://tonusername.github.io/mon-arbre-genealogique)

(Remplace `tonusername` par ton vrai username GitHub)

## 🎯 Fonctionnalités

- ✅ Navigation interactive
- ✅ Zoom et déplacement
- ✅ Générateurs contrôlables (1-5 générations)
- ✅ Bilingue (Français/Italiano)
- ✅ Détails complets au clic

## 📁 Structure

```
families/
├── rossi-bianchi/
│   ├── data.json
│   └── [personne_id]/
│       ├── info.txt
│       └── photo.jpg
└── verdi-ferrari/
    ├── data.json
    └── ...
```

## 📝 Comment ajouter une famille

1. Crée un dossier: `families/nouvelle-famille/`
2. Crée `data.json` avec les données
3. Pour chaque personne, crée un dossier:
   - `families/nouvelle-famille/personne_id/`
   - Ajoute `info.txt` et `photo.jpg`
4. Mets à jour `index.html` pour charger le nouveau JSON

[Voir CONTRIBUER.md](./CONTRIBUER.md) pour plus de détails.

## 🤝 Comment proposer des modifications

1. Fork ce repo
2. Fais tes modifications
3. Crée une Pull Request
```

---

## 📋 Étape 10: Créer `CONTRIBUER.md`

```markdown
# Comment Contribuer

## Ajouter une personne à une famille existante

### 1. Créer le dossier

```
families/rossi-bianchi/nuovo_id/
```

### 2. Créer `info.txt`

```
Nome: Nome Cognome
Nato: GG-MM-AAAA
Morto: GG-MM-AAAA (ou lasciare vuoto)
Luogo di nascita: Città
Professione: Job
Note: Qualsiasi nota
```

### 3. Ajouter les images

Ajoute jusqu'à 5 images dans le dossier (format: JPG, PNG):
- `photo1.jpg` (image 1)
- `photo2.jpg` (image 2)
- `photo3.jpg` (image 3)
- `photo4.jpg` (image 4)
- `photo5.jpg` (image 5)

Optionnel: Tu peux en ajouter moins (1, 2, 3 images...)

### 4. Modifier `families/rossi-bianchi/data.json`

Ajoute l'entrée JSON:

```json
"nuovo_id": {
  "id": "nuovo_id",
  "name": "Nome Cognome",
  "birth": "GG-MM-AAAA",
  "death": null,
  "birthPlace": "Città",
  "profession": "Job",
  "images": [
    "families/rossi-bianchi/nuovo_id/photo1.jpg"
  ],
  "notes": "Note",
  "parents": ["parent_id1"],
  "partners": [
    {
      "id": "partner_id1",
      "children": ["child_id1", "child_id2"]
    },
    {
      "id": "partner_id2",
      "children": ["child_id3"]
    }
  ]
}
```

## Spiegazione

- **`partners`**: array di oggetti (non più una stringa singola)
- Ogni partner ha:
  - **`id`**: ID del partner
  - **`children`**: array di ID dei figli con questo partner
- Puoi avere **quanti partner vuoi** e **quanti figli vuoi** con ognuno

### 5. Commit et Push

```bash
git add .
git commit -m "Aggiunto nuovo_id alla famiglia rossi-bianchi"
git push origin main
```

---

## Ajouter une nouvelle famille

1. Crée le dossier: `families/nuova-famiglia/`
2. Crée les sous-dossiers pour chaque personne
3. Crée `data.json` avec toutes les persone
4. Modifie `index.html`: ajoute le chemin vers `data.json`

## Format des données JSON

Voir [FORMAT.md](./docs/FORMAT.md)
```

---

## 📊 Étape 11: Créer `docs/FORMAT.md`

```markdown
# Format des Données JSON

## Structure d'une personne

```json
{
  "unique_id": {
    "id": "unique_id",
    "name": "Nome Cognome",
    "birth": "GG-MM-AAAA",
    "death": null,
    "birthPlace": "Città",
    "profession": "Professione",
    "image": "families/famiglia/unique_id/photo.jpg",
    "notes": "Note",
    "parents": ["parent_id1", "parent_id2"],
    "partner": "partner_id",
    "children": ["child_id1", "child_id2"]
  }
}
```

## Campi

| Campo | Tipo | Esempio | Obbligatorio? |
|-------|------|---------|---------------|
| `id` | string | `"rossi_marco"` | ✅ SÌ (unico) |
| `name` | string | `"Marco Rossi"` | ✅ SÌ |
| `birth` | string | `"15-01-1950"` | ❌ null ok |
| `death` | string \| null | `"22-03-2010"` | ❌ null ok |
| `birthPlace` | string | `"Roma"` | ❌ null ok |
| `profession` | string | `"Ingegnere"` | ❌ null ok |
| `images` | array | `["path/to/photo1.jpg", ...]` | ❌ array vide [] ok (max 5 images) |
| `notes` | string | `"Fondatore"` | ❌ null ok |
| `parents` | array \| null | `["id1", "id2"]` | ✅ null se nessun genitore |
| `partner` | string \| null | `"partner_id"` | ❌ null ok |
| `children` | array | `["id1", "id2"]` | ✅ sempre array (vuoto [] se nessun figlio) |

## Regole

- **`id`** deve essere unico in tutta l'applicazione
- **`birth` e `death`** formato: `GG-MM-AAAA`
- **`parents`** deve contenere gli ID dei genitori (massimo 2)
- **`children`** deve contenere gli ID dei figli
- **`partner`** ID della persona partner (può essere null)
```

---

## 🚀 Étape 12: Pousser sur GitHub

```bash
# Ajouter tous les fichiers
git add .

# Créer un commit
git commit -m "Initial commit: arbre généalogique structuré"

# Pousser
git push origin main
```

---

## 🌐 Étape 13: Activer GitHub Pages

1. Va sur ton repo GitHub
2. Clique **"Settings"**
3. Scroll à **"Pages"** (à gauche)
4. Sous **"Source"**, sélectionne **"main"**
5. Clique **"Save"**

Attends 1-2 minutes, puis c'est à:
```
https://tonusername.github.io/mon-arbre-genealogique
```

---

## ✅ Checklist

- [ ] Repo créé
- [ ] Structure des dossiers créée
- [ ] `data.json` pour chaque famille créé
- [ ] `info.txt` pour chaque personne
- [ ] Photos ajoutées
- [ ] `index.html` modifié
- [ ] `README.md` + `CONTRIBUER.md` créés
- [ ] Commit et push
- [ ] GitHub Pages activé

---

## 🎓 C'est bon!

Ton arbre généalogique est maintenant en ligne! 🎉

Pour ajouter des personnes/familles à l'avenir:
1. Crée les dossiers
2. Ajoute les données JSON
3. Commit et push!

Besoin d'aide? Crée une Issue! 😊
