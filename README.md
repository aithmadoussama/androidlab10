# LAB 10 — Navigation Drawer & Fragments Android

## 📌 Description

Ce projet Android présente l’utilisation :

- du **Navigation Drawer**
- des **Fragments**
- du **FragmentManager**
- de la navigation entre plusieurs écrans dans une seule activité.

L’application permet de changer dynamiquement le contenu affiché grâce à un menu latéral.

---

# 🎯 Objectifs pédagogiques

Ce TP permet de comprendre :

- la structure d’un `DrawerLayout`
- l’utilisation du `NavigationView`
- la gestion des `Fragments`
- la navigation dans Android
- le remplacement dynamique des vues avec `FragmentManager`

---

# 🛠 Technologies utilisées

- Java
- Android Studio
- Android SDK
- Material Design
- Navigation Drawer
- Fragments

---

# 📂 Structure du projet

```text
lab10/
│
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/lab10/
│   │   │   │   ├── MainActivity.java
│   │   │   │   ├── BlankFragment.java
│   │   │   │   ├── BlankFragment2.java
│   │   │   │   └── FragmentList.java
│   │   │   │
│   │   │   ├── res/
│   │   │   │   ├── layout/
│   │   │   │   ├── menu/
│   │   │   │   │   └── drawer_menu.xml
│   │   │   │   └── drawable/
│   │   │   │
│   │   │   └── AndroidManifest.xml
│
├── build.gradle.kts
└── settings.gradle.kts
```

---

# 🚀 Fonctionnalités

## 1️⃣ Navigation Drawer

L’application contient un menu latéral permettant de naviguer entre plusieurs fragments.

### Menu disponible

- Fragment 1
- Fragment 2
- Liste

---

## 2️⃣ Gestion des Fragments

Lorsqu’un utilisateur clique sur un élément du menu :

- le fragment actuel est remplacé
- le nouveau fragment est affiché dans le conteneur principal

---

## 3️⃣ Navigation dynamique

Le changement de vue est effectué avec :

```java
getSupportFragmentManager()
        .beginTransaction()
        .replace(R.id.contenu, new BlankFragment())
        .commit();
```

---

# 🖥 Interface utilisateur

L’application utilise :

- `DrawerLayout`
- `NavigationView`
- `FrameLayout`
- plusieurs `Fragments`

---

# 📖 Explication des composants

---

## 🔹 DrawerLayout

Le `DrawerLayout` est le conteneur principal.

Il permet d’afficher :

- le contenu principal
- le menu latéral

### Exemple

```xml
<androidx.drawerlayout.widget.DrawerLayout>
```

---

## 🔹 NavigationView

Le `NavigationView` contient les éléments du menu.

### Exemple

```xml
<com.google.android.material.navigation.NavigationView
    app:menu="@menu/drawer_menu" />
```

---

## 🔹 FrameLayout

Le `FrameLayout` sert de conteneur pour les fragments.

### Exemple

```xml
<FrameLayout
    android:id="@+id/contenu" />
```

---

## 🔹 Fragment

Un Fragment représente une partie réutilisable de l’interface utilisateur.

### Fragments utilisés

| Fragment | Rôle |
|---|---|
| BlankFragment | Premier écran |
| BlankFragment2 | Deuxième écran |
| FragmentList | Affichage liste |

---

# 📂 Fichier activity_main.xml

```xml
<?xml version="1.0" encoding="utf-8"?>

<androidx.drawerlayout.widget.DrawerLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/drawer_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <FrameLayout
        android:id="@+id/contenu"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

    <com.google.android.material.navigation.NavigationView
        android:id="@+id/nav_view"
        android:layout_width="wrap_content"
        android:layout_height="match_parent"
        android:layout_gravity="start"
        app:menu="@menu/drawer_menu" />

</androidx.drawerlayout.widget.DrawerLayout>
```

---

# 📂 Fichier drawer_menu.xml

```xml
<?xml version="1.0" encoding="utf-8"?>

<menu xmlns:android="http://schemas.android.com/apk/res/android">

    <item
        android:id="@+id/nav_fragment1"
        android:title="Fragment 1" />

    <item
        android:id="@+id/nav_fragment2"
        android:title="Fragment 2" />

    <item
        android:id="@+id/nav_list"
        android:title="Liste" />

</menu>
```

---

# 📂 MainActivity.java

L’activité principale gère :

- les clics du menu
- le changement des fragments
- la fermeture du menu latéral

---

# ▶️ Exécution du projet

## 1️⃣ Ouvrir le projet

Dans Android Studio :

```text
File → Open → lab10
```

---

## 2️⃣ Synchroniser Gradle

Android Studio télécharge automatiquement les dépendances.

---

## 3️⃣ Ajouter la dépendance Material Design

Dans :

```text
build.gradle.kts
```

ajouter :

```kotlin
implementation("com.google.android.material:material:1.12.0")
```

Puis :

```text
Sync Now
```

---

## 4️⃣ Lancer l’application

- connecter un téléphone Android
- ou utiliser un émulateur

Puis cliquer sur :

```text
Run ▶
```

---

# 📸 Résultat attendu

- affichage du menu latéral
- navigation fluide entre les fragments
- remplacement dynamique du contenu
- interface moderne Material Design

---

# ⚠️ Remarques importantes

- le dossier `menu` doit être créé manuellement
- chaque Fragment possède son propre layout XML
- le `NavigationView` nécessite la bibliothèque Material Design

---

# 👨‍💻 Auteur

Projet pédagogique Android — LAB 10

---
