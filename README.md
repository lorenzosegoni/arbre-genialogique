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

families/
├── rossi-bianchi/
│   ├── data.json
│   └── [personne_id]/
│       ├── info.txt
│       └── photo.jpg
└── verdi-ferrari/
├── data.json
└── ...

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
| `image` | string | `"path/to/photo.jpg"` | ❌ null ok |
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
