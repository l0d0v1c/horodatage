# 🔐 OpenTimestamps - Application d'horodatage sur Bitcoin

Application web permettant de créer et vérifier des horodatages cryptographiques sur la blockchain Bitcoin en utilisant OpenTimeStamps.

# Accès rapide
[Accéder ici](https://l0d0v1c.github.io/horodatage/)

## 📋 Table des matières

- [Qu'est-ce que c'est ?](#quest-ce-que-cest-)
- [Fonctionnalités](#fonctionnalités)
- [Installation](#installation)
- [Utilisation](#utilisation)
  - [1. Créer un horodatage](#1-créer-un-horodatage)
  - [2. Vérifier un horodatage](#2-vérifier-un-horodatage)
  - [3. Gérer sa bibliothèque](#3-gérer-sa-bibliothèque)
- [Comment ça marche ?](#comment-ça-marche-)
- [FAQ](#faq)
- [Limitations](#limitations)

## Qu'est-ce que c'est ?

OpenTimestamps permet de prouver qu'un document existait à un moment précis en l'ancrant sur la blockchain Bitcoin. C'est utile pour :

- 📄 **Protéger la propriété intellectuelle** (documents, créations, brevets)
- 📝 **Certifier des contrats** et accords
- 🖼️ **Prouver l'antériorité** d'une œuvre
- 🔒 **Garantir l'intégrité** de fichiers importants
- 📊 **Traçabilité** de données sensibles

**Avantages :**
- ✅ Gratuit et décentralisé
- ✅ Preuve mathématiquement infalsifiable
- ✅ Fonctionne avec n'importe quel type de fichier
- ✅ Confidentialité totale (seul le hash est publié, pas le contenu)

## Fonctionnalités

### ✨ Création d'horodatages
- 📁 Horodater n'importe quel fichier
- ✍️ Horodater du texte directement
- 💾 Calcul du hash SHA-256
- 📥 Téléchargement automatique du fichier `.ots`

### 🔍 Vérification d'horodatages
- ✅ Vérifier l'authenticité d'un fichier
- 📅 Voir la date exacte d'enregistrement sur Bitcoin
- 🔗 Lien direct vers le bloc Bitcoin
- 🔄 Mise à jour automatique des timestamps

### 📚 Bibliothèque locale
- 💾 Sauvegarde automatique dans le navigateur
- 🔄 Vérification et mise à jour en un clic
- 📥 Téléchargement des fichiers `.ots`
- 💾 Export/import de la bibliothèque complète
- 🗑️ Gestion des fichiers horodatés

### 📱 Interface moderne
- Responsive (mobile/tablette/desktop)
- Design épuré et intuitif
- Thème clair optimisé pour la lisibilité

## Installation

### Prérequis
- Un navigateur web moderne (Chrome, Firefox, Safari, Edge)
- La bibliothèque `opentimestamps.min.js`

### Étapes

1. **Cloner ou télécharger** le projet :
```bash
git clone https://github.com/votre-repo/OpenTimeStamps.git
cd OpenTimeStamps
```

2. **Télécharger la bibliothèque OpenTimestamps** :
   - Téléchargez `opentimestamps.min.js` depuis [OpenTimestamps JavaScript](https://github.com/opentimestamps/javascript-opentimestamps)
   - Placez le fichier dans le même dossier que `OpenTimestampsv2.html`

3. **Ouvrir l'application** :
   - Double-cliquez sur `OpenTimestampsv2.html`
   - Ou utilisez un serveur web local :
```bash
python3 -m http.server 8000
# Puis ouvrez http://localhost:8000/OpenTimestampsv2.html
```

## Utilisation

### 1. Créer un horodatage

#### Option A : Horodater un fichier

1. Cliquez sur l'onglet **"Créer un horodatage"**
2. Sélectionnez **"📁 Fichier"**
3. Cliquez sur la zone de dépôt ou glissez-déposez votre fichier
4. Le hash SHA-256 est calculé automatiquement
5. Cliquez sur **"Créer l'horodatage"**
6. Deux fichiers sont téléchargés :
   - Votre fichier original (en mode texte uniquement)
   - Le fichier `.ots` (preuve d'horodatage)

#### Option B : Horodater du texte

1. Cliquez sur l'onglet **"Créer un horodatage"**
2. Sélectionnez **"✍️ Texte"**
3. Tapez ou collez votre texte
4. Le hash est calculé en temps réel
5. Cliquez sur **"Créer l'horodatage"**
6. Le fichier texte ET le fichier `.ots` sont téléchargés

#### 📝 Important
- Le fichier `.ots` est **petit** (quelques Ko) et contient la preuve cryptographique
- **Conservez le fichier original ET le fichier `.ots`** ensemble
- L'horodatage initial est en "attente" car il doit être confirmé sur Bitcoin
- La confirmation peut prendre **plusieurs heures** (temps d'inclusion dans un bloc Bitcoin)

### 2. Vérifier un horodatage

1. Cliquez sur l'onglet **"Vérifier un horodatage"**
2. **Sélectionnez le fichier `.ots`** (fichier de preuve)
3. **Sélectionnez le fichier original** (celui qui a été horodaté)
4. Cliquez sur **"Vérifier l'horodatage"**

#### Résultats possibles :

**✅ Horodatage vérifié avec succès**
- Le fichier est authentique
- Affichage de :
  - La blockchain (Bitcoin)
  - Le numéro de bloc
  - La date et heure exactes
  - Le timestamp Unix
  - Un lien vers le bloc sur blockchain.com

**⏳ Horodatage non encore confirmé**
- Le fichier est en attente de confirmation
- Une mise à jour peut être disponible
- Revenez plus tard pour vérifier à nouveau

**❌ Erreur**
- Le fichier original ne correspond pas au fichier `.ots`
- Le fichier `.ots` est corrompu
- Format de fichier invalide

#### 🔄 Mise à jour d'un timestamp

Si un bouton **"📥 Télécharger le fichier .ots mis à jour"** apparaît :
- Cliquez dessus pour obtenir la version complète avec les attestations Bitcoin
- Remplacez votre ancien fichier `.ots` par la nouvelle version
- Cette version mise à jour contient la preuve complète de la blockchain

### 3. Gérer sa bibliothèque

L'application sauvegarde automatiquement tous vos horodatages dans le navigateur (localStorage).

#### Accéder à la bibliothèque
1. Cliquez sur l'onglet **"📚 Ma bibliothèque"**
2. Visualisez tous vos fichiers horodatés

#### Fonctionnalités disponibles

**Pour chaque fichier :**
- **📥 Télécharger .ots** : Récupérer le fichier de preuve
- **🔄 Vérifier & MAJ** : Vérifier si une mise à jour est disponible (apparaît si le fichier n'est pas à jour)
- **🗑️ Supprimer** : Retirer le fichier de la bibliothèque

**Statuts des fichiers :**
- ✅ **À jour** : Le fichier est confirmé sur Bitcoin
- ⏳ **En attente** : Le fichier attend la confirmation blockchain

#### 💾 Sauvegarder la bibliothèque

Exportez votre bibliothèque pour la partager entre appareils ou en faire une sauvegarde :

1. Cliquez sur **"💾 Sauvegarder"**
2. Un fichier JSON est téléchargé : `opentimestamps_library_YYYYMMDD_HHMM.json`
3. Conservez ce fichier en lieu sûr

**Le fichier contient :**
- Tous les noms de fichiers
- Les hash SHA-256
- Les données `.ots` complètes
- Les métadonnées (dates, statuts)

#### 📂 Restaurer la bibliothèque

Importez une bibliothèque sauvegardée précédemment :

1. Cliquez sur **"📂 Restaurer"**
2. Sélectionnez votre fichier JSON de sauvegarde
3. Choisissez le mode d'importation :
   - **OUI (Fusionner)** : Ajoute les fichiers sans écraser les existants (pas de doublons)
   - **NON (Remplacer)** : Supprime la bibliothèque actuelle et la remplace

#### 🔄 Actualiser

Cliquez sur **"🔄 Actualiser"** pour recharger l'affichage de la bibliothèque.

## Comment ça marche ?

### Principe technique

1. **Calcul du hash** : L'application calcule le hash SHA-256 de votre fichier
   ```
   Fichier → SHA-256 → Hash unique (64 caractères hexadécimaux)
   ```

2. **Création du timestamp** : Le hash est envoyé aux serveurs OpenTimestamps qui :
   - Agrègent plusieurs hash ensemble (Merkle tree)
   - Ancrent le hash dans une transaction Bitcoin
   - Génèrent un fichier `.ots` contenant la preuve cryptographique

3. **Confirmation blockchain** : Une fois le bloc Bitcoin miné :
   - Le timestamp devient permanent et immuable
   - Il est impossible de le modifier rétroactivement
   - La date est garantie par le consensus Bitcoin

4. **Vérification** : Pour vérifier :
   - On recalcule le hash du fichier
   - On suit le chemin cryptographique dans le fichier `.ots`
   - On vérifie que le hash final correspond à ce qui est dans le bloc Bitcoin

### Pourquoi c'est fiable ?

- 🔒 **Cryptographie** : SHA-256 est pratiquement impossible à inverser
- ⛓️ **Bitcoin** : La blockchain Bitcoin est la plus sécurisée au monde
- 📊 **Merkle trees** : Permet d'ancrer des milliers de hash en une seule transaction
- ⏱️ **Preuve temporelle** : Le bloc Bitcoin prouve qu'on ne peut pas antidater

### Confidentialité

- ✅ Seul le **hash** est publié, jamais le contenu du fichier
- ✅ Personne ne peut retrouver le fichier original à partir du hash
- ✅ Vous pouvez horodater des documents confidentiels en toute sécurité

## FAQ

### ❓ Combien de temps faut-il pour qu'un horodatage soit confirmé ?

En général, entre **1 à 6 heures**, le temps que le prochain bloc Bitcoin soit miné et que le serveur OpenTimestamps agrège les timestamps.

### ❓ Est-ce vraiment gratuit ?

Oui ! OpenTimestamps est un service gratuit et open-source. Les coûts de transaction Bitcoin sont mutualisés entre tous les utilisateurs.

### ❓ Puis-je horodater des fichiers volumineux ?

Oui, la taille importe peu car seul le hash est utilisé. Vous pouvez horodater :
- Un petit document texte
- Une vidéo de plusieurs Go
- Une base de données complète

### ❓ Que se passe-t-il si je perds le fichier `.ots` ?

Si vous avez ajouté le fichier à la bibliothèque, vous pouvez le télécharger à nouveau. Sinon, vous devrez recréer l'horodatage (avec une nouvelle date).

### ❓ Le fichier `.ots` suffit-il comme preuve ?

Non, il faut **les deux** :
- Le fichier original (pour calculer le hash)
- Le fichier `.ots` (pour prouver l'ancrage sur Bitcoin)

### ❓ Puis-je partager ma bibliothèque entre plusieurs appareils ?

Oui ! Utilisez les boutons **Sauvegarder** et **Restaurer** pour exporter/importer votre bibliothèque au format JSON.

### ❓ Mes données sont-elles stockées en ligne ?

Non. Tout est stocké **localement** dans votre navigateur (localStorage). Si vous videz le cache du navigateur, vous perdrez la bibliothèque (d'où l'importance de sauvegarder).

### ❓ Puis-je utiliser cette application hors ligne ?

Partiellement :
- ✅ Calcul du hash : Oui
- ❌ Création d'horodatage : Non (nécessite Internet pour contacter les serveurs)
- ✅ Vérification initiale : Oui (si le `.ots` est déjà complet)
- ❌ Mise à jour des timestamps : Non

### ❓ Quelle est la valeur légale d'un horodatage OpenTimestamps ?

OpenTimestamps fournit une **preuve technique** d'antériorité. La valeur légale dépend de votre juridiction. Consultez un avocat pour des questions juridiques spécifiques.

### ❓ Puis-je faire confiance à cette application ?

- ✅ Code open-source (vous pouvez l'inspecter)
- ✅ Utilise la bibliothèque officielle OpenTimestamps
- ✅ Aucune donnée n'est envoyée à un serveur tiers (sauf le hash aux serveurs OpenTimestamps)
- ✅ Tout fonctionne en local dans votre navigateur

## Limitations

- 📱 **LocalStorage** : Limité à ~5-10 Mo selon les navigateurs (environ 50-200 fichiers dans la bibliothèque)
- 🌐 **Connexion Internet** : Nécessaire pour créer et mettre à jour les timestamps
- ⏱️ **Délai de confirmation** : 1 à 6 heures minimum (dépend de Bitcoin)
- 🗑️ **Cache du navigateur** : Si vous videz le cache, vous perdez la bibliothèque (pensez à sauvegarder)

## Licence

Ce projet utilise OpenTimestamps qui est sous licence LGPL-3.0.

## Liens utiles

- 🌐 [Site officiel OpenTimestamps](https://opentimestamps.org/)
- 📚 [Documentation OpenTimestamps](https://github.com/opentimestamps/opentimestamps-client)
- 💻 [Bibliothèque JavaScript](https://github.com/opentimestamps/javascript-opentimestamps)
- 🔍 [Explorateur Bitcoin](https://www.blockchain.com/explorer)

## Support

Pour toute question ou problème, consultez :
- La section [FAQ](#faq) ci-dessus
- Les [issues GitHub](https://github.com/opentimestamps/javascript-opentimestamps/issues)
- La documentation officielle OpenTimestamps

---

**Fait avec ❤️ en utilisant OpenTimestamps et Bitcoin**
