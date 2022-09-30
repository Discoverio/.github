# .github
Répository de templates github actions

## Créer un template

- [ ] Créez un fichier .yml comme d'habitude, dans le répertoire `.github\workflow-templates`
- [ ] Ajouter un fichier qui portera le même nom que le workflow, avec pour extension `.properties.json`

Le ficheir `<nom-workflow>.properties.json` doit contenir à minima les informations suivantes : 

```json
{
    "name": "Buil et test sur NodeJs",
    "description": "Lancement d'un build et des tests unitaires sur NodeJs, version 16 et 18",
}
```

Pour utiliser le template, rendez-vous dans la section "Actions" du répo souhaité, puis cliquer sur "New Workflow".
Le template apparaitra dans la liste des workflows proposés
