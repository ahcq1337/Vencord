# Ajoutez Vencord et Téléchargez des plugins personnalisés

> [!CAUTION]  
> Vencord enfreint les T.O.S., je ne suis en aucun cas responsable de vos actes.

> [!TIP]  
> Ce tutoriel a été conçu avec Visual Studio Code. Vous pouvez utiliser n'importe quel IDE, mais si vous ne vous y connaissez pas, installez VSCode :  
> https://code.visualstudio.com/download

---

### Étape 1

Assurez-vous d'avoir `Git` et `Node.JS` sur votre ordinateur.  

> Git : https://git-scm.com/downloads  
> Node.JS : https://nodejs.org/en/download

---

### Étape 2

Ouvrez un terminal à l'emplacement où vous souhaitez installer Vencord et rendez-vous-y :

```bash
git clone https://github.com/Vendicated/Vencord.git
```

```bash
cd Vencord
```

> [!WARNING]  
> Le dossier ne doit pas être déplacé ensuite.

---

### Étape 3

Installez `pnpm` :

```bash
npm i -g pnpm
```

Puis vérifiez qu'il est bien installé :

```bash
pnpm --version
```

Vous devriez avoir un retour comme :

```bash
10.4.1
```

Installez les dépendances :

```bash
pnpm i
```

---

### Étape 4

Mettez à jour Vencord :

```bash
pnpm build
```

Assurez-vous que Discord soit complètement fermé en arrière-plan.

> [!TIP]  
> Vous pouvez exécuter la commande suivante dans un terminal ou via `Win + R` :
> ```bash
> taskkill /f /im discord.exe
> ```

Injectez Vencord :

```bash
pnpm inject
```

> [!TIP]  
> Si vous possédez Canary ou PTB, sélectionnez l'instance sur laquelle vous souhaitez injecter Vencord.

---

### Étape 5

Rendez-vous dans `src` et créez un dossier `userplugins` avec les commandes suivantes ou manuellement :

```bash
cd src
```

```bash
mkdir userplugins
```

```bash
cd userplugins
```

---

### Étape 6

Vous pouvez télécharger divers plugins créés par la communauté avec la commande suivante :

```bash
git clone <lien du repo se finissant par .git>
```

N'oubliez pas de mettre à jour à chaque nouveau plugin ou modification :

```bash
pnpm build
```

Puis relancez Discord ou effectuez `Ctrl + R` pour rafraîchir.

Vous trouverez les nouveaux plugins dans la section Plugins de Vencord dans vos paramètres. Activez-les et relancez Discord.

---

# Créez vos propres plugins

> [!TIP]  
> Il est conseillé d'avoir les bases en JavaScript ou en TypeScript afin de créer vos propres plugins.  
> Les fichiers seront en `.tsx` ou `.jsx`.

Vous devez avoir suivi la première partie du tutoriel pour créer vos plugins.

Rendez-vous dans le dossier `userplugins` créé précédemment.  
Créez un sous-dossier avec le nom de votre plugin avec la commande suivante ou manuellement :

```bash
mkdir <nom-du-plugin>
```

Et à l'intérieur, créez un fichier `.tsx` (TypeScript) ou `.jsx` (JavaScript).

Voici le modèle d'un fichier `.jsx` :

```jsx
/*
 * Vencord, a Discord client mod
 * Copyright (c) 2025 Vendicated and contributors
 * SPDX-License-Identifier: GPL-3.0-or-later
 */

import definePlugin from "@utils/types";

export default definePlugin({
    name: "nom du plugin",
    description: "description du plugin",
    authors: [{ name: "votre pseudo", id: 0 }],
});
```

Créer un plugin peut être difficile, mais vous pouvez regarder le code source de plugins publics pour vous inspirer et vous aider.
