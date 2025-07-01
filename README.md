<p align="center">
  <img src="https://user.oc-static.com/upload/2025/02/18/1739888335313_Capture_d_e%CC%81cran_2025-02-18_a%CC%80_16.17.46-removebg-preview.png" alt="ARISTA logo" width="150"/>
</p>

# 💡 Projet Android - ARISTA  📱🧠

> 🚀 Continuation du **Projet 5** dans le cadre de notre mission avec la startup fictive **ARISTA** !

---

## 🌟 Objectif

🎯 Dans cet exercice, votre mission est de **persister les données** à l'aide de la librairie **Room** dans une application Android comportant **trois fragments spécifiques** intégrés dans une activité.

---

## 🧱 Architecture prévue

L'application se base sur votre diagramme de classes précédent. Vous devez y intégrer **Room** afin de garantir la persistance des données, même après une **rotation d’écran** ou un **redémarrage de l'application**.

---

## 🧩 Les 3 Fragments

| Fragment | Données | Modification possible ? |
|---------|---------|--------------------------|
| 👤 Utilisateur | Préremplies à la création de la base | ❌ Aucune modification |
| 🏋️ Exercices | Création via un FAB ➕ / Suppression via l'interface ❌ | ✅ Ajout / ✅ Suppression |
| 😴 Sommeil | Préremplies à la création de la base | ❌ Aucune modification |

---

## 🎨 Ce qui est déjà prêt

✅ **UI/UX** : la conception graphique de l'application est **déjà en place** !

🎨 Vous n'avez plus qu'à **connecter les données** grâce à Room.

---

## 🛠️ Ce que vous devez faire

1. 🔄 Reprendre votre **diagramme de classes**.
2. 🧠 Ajouter **Room** à votre projet :
   - Créer les entités, DAO, et base de données.
   - Gérer la création de la base avec pré-remplissage.
3. 📲 Gérer la persistance dans vos **ViewModel**.
4. ➕ Ajouter un **Floating Action Button (FAB)** pour créer des exercices.
5. ❌ Gérer la suppression d’un exercice via l’interface dédiée.

> 🎨 Vous avez **carte blanche** pour la structure et le style. L’objectif est de **rendre les données persistantes avec Room**. Faites-vous plaisir !

---

## 📚 Technologies utilisées

- 🟦 Kotlin
- 🏗️ MVVM
- 🏠 Room
- 📦 LiveData / StateFlow
- ✨ Material Components

---

## 📦 Exemple de structure Room

```kotlin
@Entity
data class Exercise(
    @PrimaryKey(autoGenerate = true) val id: Int = 0,
    val name: String,
    val duration: Int // en minutes
)

@Dao
interface ExerciseDao {
    @Insert fun insert(exercise: Exercise)
    @Delete fun delete(exercise: Exercise)
    @Query("SELECT * FROM Exercise") fun getAll(): LiveData<List<Exercise>>
}
