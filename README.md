# Project-1-Clustering-
🧠 Sammenligning af clustering på 2D vs højdimensionelt datasæt
🔹 Datasæt 1: 2D (R15)
Valgt algoritme: DBSCAN
Hvorfor:
Datasættet består af tætte, klart adskilte clusters
DBSCAN er god til:
at finde naturlige grupper
at håndtere støj (outliers)
Resultater:
DBSCAN fandt 15 clusters (korrekt)
Identificerede også støjpunkter (-1)
Gav en god visuel struktur i scatter plot
Parametervalg:
eps ≈ 0.5
min_samples = 4–5
Evaluering:
Silhouette score var høj (~0.79)
Men vigtigst: visuel struktur passede perfekt
Konklusion:
DBSCAN er meget velegnet til 2D datasættet, da det kan identificere tætte, veladskilte clusters og samtidig håndtere støj. Kvalitetsmål som silhouette stemmer godt overens med den visuelle struktur.
🔹 Datasæt 2: Højdimensionelt (D = 1024)
Valgt algoritme: K-means (og GMM)
Hvorfor ikke DBSCAN:
I høj dimension opstår curse of dimensionality
Afstande bliver mindre meningsfulde
DBSCAN bliver:
ustabil
meget følsom over for eps
🥇 K-means
Hvorfor:
Datasættet består af Gaussian clusters
K-means fungerer godt til:
kompakte, runde clusters
højdimensionelle data
Resultater:
Finder ca. 16 clusters
Stabil løsning
God silhouette score
🥈 GMM (Gaussian Mixture Model)
Hvorfor:
Mere fleksibel end K-means
Kan modellere:
forskellig varians
elliptiske clusters
Resultater:
Sammenlignelig eller lidt bedre end K-means
Giver probabilistisk fortolkning
📊 Evaluering
Silhouette score blev brugt
PCA blev brugt til visualisering (fra 1024D → 2D)
👉 vigtigt:
visualisering er kun en projektion
clustering sker stadig i høj dimension
⚠️ Vigtig forskel mellem datasæt
Egenskab	2D datasæt	1024D datasæt
Struktur	Tydelige klumper	Gaussian blobs
Bedste metode	DBSCAN	K-means / GMM
Støj	Relevant	Mindre relevant
Visualisering	Direkte	Kræver PCA
🔍 Om kvalitetsmål
Silhouette score:
fungerede godt i begge tilfælde
men:
👉 i DBSCAN:
må ikke bruges alene
skal kombineres med:
støj
visuel struktur
👉 i K-means/GMM:
mere direkte anvendelig
🎯 Samlet konklusion
For det todimensionelle datasæt er DBSCAN mest velegnet, da det kan identificere tætte clusters og håndtere støj effektivt. For det højdimensionelle datasæt er K-means og GMM mere passende, da afstandsbaserede tæthedsmetoder som DBSCAN bliver mindre effektive i høj dimension. Valg af algoritme afhænger derfor i høj grad af datastruktur og dimensionalitet.
📌 Kobling til opgave (vigtigt)
Din opgave spørger bl.a.:
“Which algorithm is most suitable for the dataset?”
👉 dit svar er nu:
2D → DBSCAN
1024D → K-means / GMM
