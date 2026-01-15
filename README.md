# 🛒 OnlineRetailDB - Aplicație WPF pentru Retail Online

O aplicație desktop completă pentru un magazin online, dezvoltată în **C# WPF** folosind arhitectura **MVVM** (Model-View-ViewModel) și **Entity Framework** pentru accesul la baza de date.

---

## 📋 Cuprins

1. [Descriere Generală](#descriere-generală)
2. [Arhitectura Proiectului](#arhitectura-proiectului)
3. [Structura Folderelor](#structura-folderelor)
4. [Modele (Models)](#modele-models)
5. [ViewModels](#viewmodels)
6. [Views](#views)
7. [Services](#services)
8. [Utilities](#utilities)
9. [Fluxul Aplicației](#fluxul-aplicației)
10. [Diagrama Relațiilor din Baza de Date](#diagrama-relațiilor-din-baza-de-date)
11. [Cum să Rulezi Proiectul](#cum-să-rulezi-proiectul)

---

## 📖 Descriere Generală

**OnlineRetailDB** este o aplicație de tip e-commerce care permite:

- ✅ Înregistrarea și autentificarea utilizatorilor (Clienți și Administratori)
- ✅ Navigarea în magazin cu filtrare pe categorii și căutare
- ✅ Adăugarea produselor în coș și finalizarea comenzilor
- ✅ Vânzarea de produse de către utilizatori (rol de vânzător)
- ✅ Gestionarea comenzilor pending – expediere simultană a tuturor produselor dintr-o comandă
- ✅ Istoricul comenzilor și vânzărilor
- ✅ Panou de administrare pentru gestionarea utilizatorilor, produselor și statisticilor

---

## 🏗️ Arhitectura Proiectului

Proiectul folosește arhitectura **MVVM**:

