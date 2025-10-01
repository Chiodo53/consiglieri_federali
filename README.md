# Creare cartelle
mkdir docs
mkdir data
mkdir notebooks_jupyter

# Creare un file dentro ogni cartella
echo "# Documentation" > docs/documentation.md
echo "" > data/.gitkeep

# Aggiungere tutto al repository
git add .
git commit -m "Aggiunte cartelle docs, data e notebooks_jupyter"
git push
