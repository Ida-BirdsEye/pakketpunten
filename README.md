# 📦 Pakketpunten Data

Een Python-project voor het **verzamelen, analyseren en visualiseren van pakketpunten in Nederland**.  
De data wordt opgehaald via verschillende API’s (zoals DHL en De Buren), geanalyseerd met **GeoPandas**,  
en weergegeven als interactieve kaarten met **Folium**.

Dit project is bedoeld als basis voor geodata-analyse, ruimtelijke visualisatie en verdere uitbreiding naar een webapplicatie.

---

## Functionaliteiten

- Ophalen van pakketpuntlocaties via API’s en webscraping (voor DHL, De Buren, PostNL en VintedGo) voor een gegeven gemeente
- Het toevoegen van buffers rondom bestaande pakketpunten
- Het toevoegen van dummy data met de bezettingsgraad om een indicatie te geven van hoe de dekking van een gebied kan worden bepaald.
- Export van resultaten naar **GeoPackage (.gpkg)** en **GeoJSON (.geojson)**  
- Interactieve kaartweergave in **Folium**, opgeslagen als HTML 

---

## Projectstructuur

```
project/
├── main.py             # Hoofdscript: haalt de data io, voert de analyse en kaartgeneratie uit
├── api_client.py       # API-aanroepen (DHL, De Buren, etc.)
├── utils.py            # Algemene hulpfuncties
├── geo_analysis.py     # Geografische analyses (buffers, unions, etc.)
├── visualize.py        # Kaartweergave met Folium
├── output/             # Opslag van resultaten (GeoPackage, GeoJSON, HTML)
├── requirements.txt    # Benodigde Python-pakketten
└── README.md           # Projectdocumentatie
```

---

## Gebruik

### Installatie

```bash
git clone https://github.com/Ida-BirdsEye/pakketpunten.git
cd pakketpunten
pip install -r requirements.txt
```

### Uitvoeren
Voer het hoofdscript uit om de pakketpunten data op te halen en te visualiseren:

```bash
python main.py
```

De resultaten worden opgeslagen in de map `output/`.

### Resultaten bekijken
- **Kaart:** `output/kaart.html` → open in je browser  
- **GeoPackage / GeoJSON:** open in QGIS, GeoPandas of een andere GIS-tool  

---

## Visualisatie

De interactieve kaart wordt gemaakt met **Folium**.  
Je kunt de kaart openen in een webbrowser.

Voorbeeldweergave (vereenvoudigd):

```python
from visualize import create_map

m = create_map(gdf_pakketpunten, buffer_union300, buffer_union500)
m.save("output/kaart.html")
```

---

## Technische details

- **Taal:** Python 3.10+  
- **Belangrijkste libraries:**
  - geopandas
  - shapely
  - folium
  - requests
  - fiona
  - pandas
- **Bestandsformaten:**
  - .gpkg → GeoPackage (voor GIS-software)
  - .geojson → Webvriendelijk formaat
  - .html → Interactieve kaartweergave  

---

## Toekomstige uitbreidingen

- work-in-progress..

---

## Licentie

Dit project is vrijgegeven onder de **MIT-licentie**.  
Je mag de code gebruiken, aanpassen en verspreiden zolang de originele auteursvermelding behouden blijft.

---

> voeg een screenshot toe van een voorbeeld van de kaart in `docs/screenshot.png`  
> en verwijs ernaar in deze README:
> ```markdown
> ![Voorbeeldkaart](docs/screenshot.png)
> ```

