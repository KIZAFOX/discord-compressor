# Discord Compressor

Compresse une vidéo directement dans le navigateur pour qu'elle passe sous la limite d'envoi de Discord.

**👉 https://kizafox.github.io/discord-compressor/**

## Fonctionnement

1. Glisse une vidéo dans la page.
2. Choisis la taille max : 10 Mo (Discord gratuit), 50 Mo (Nitro Basic), 500 Mo (Nitro) ou une taille personnalisée.
3. Clique sur **Compresser**, puis sur **Télécharger**.

- Tout se passe en local : la vidéo n'est jamais envoyée sur un serveur.
- Le débit vidéo est calculé à partir de la durée et de la taille cible, et la résolution baisse si besoin (1080p → 360p).
- Si le résultat dépasse encore la limite, la compression recommence avec un débit plus bas (3 essais max).
- Option pour retirer le son et garder plus de place pour l'image.
- Sortie en MP4 (H.264 + AAC), lu directement dans Discord.

## Technique

Un seul fichier `index.html`, sans build. L'encodage utilise [WebCodecs](https://developer.mozilla.org/docs/Web/API/WebCodecs_API) via la bibliothèque [Mediabunny](https://mediabunny.dev).

Navigateurs : Chrome et Edge récents recommandés.

## Lancer en local

```bash
python -m http.server 8000
```

Puis ouvrir http://localhost:8000.
