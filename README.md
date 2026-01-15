# 🛒 OnlineRetailDB  
### Aplicație Desktop WPF pentru Retail Online (C# · MVVM · Entity Framework)

**OnlineRetailDB** este o aplicație desktop de tip e-commerce, dezvoltată în **C# WPF**, care implementează arhitectura **MVVM (Model–View–ViewModel)** și utilizează **Entity Framework (Database First)** pentru persistența datelor.  
Aplicația acoperă întregul flux al unui magazin online: autentificare, navigare produse, coș de cumpărături, plasare comenzi, vânzări, precum și un panou de administrare.

---

## 📌 Funcționalități Principale

### Utilizatori
- Înregistrare și autentificare securizată
- Roluri distincte:
  - **Customer** – cumpără și vinde produse
  - **Admin** – gestionează utilizatori și produse
- Sesiune activă gestionată centralizat

### Magazin Online
- Listare produse cu:
  - Filtrare pe categorii
  - Căutare text
- Vizualizare detalii produs
- Adăugare produse în coș

### Coș & Comenzi
- Gestionare coș de cumpărături
- Finalizare comandă (checkout)
- Selectare:
  - Profil de facturare
  - Cont bancar
- Istoric comenzi pentru cumpărători

### Vânzări (Seller Dashboard)
- Listare produse proprii
- Vizualizare **comenzi pending**
- Gruparea comenzilor după `OrderID`
- Funcționalitate cheie:
  - **Ship All Items** – expedierea simultană a tuturor produselor dintr-o comandă

### Administrare
- Gestionare utilizatori
- Gestionare produse
- Vizualizare statistici și rapoarte

---

## 🏗️ Arhitectură

Aplicația respectă strict arhitectura **MVVM**:
  View (XAML)
  ↓ Data Binding
  ViewModel (Logică UI + Commands)
  ↓ Entity Framework
  Model (Entități DB)


### Principii respectate
- Separarea clară a responsabilităților
- Zero logică de business în Views
- Comenzi (`ICommand`) pentru orice acțiune UI
- Binding bidirecțional unde este necesar

---

## 📁 Structura Proiectului
RetailDB/
│
├── Database/
│ └── table_creation.sql
│
├── Models/
│ ├── RetailDB.edmx
│ ├── User.cs
│ ├── Item.cs
│ ├── Order.cs
│ ├── OrderDetail.cs
│ ├── Category.cs
│ ├── BankAccount.cs
│ ├── BillingProfile.cs
│ ├── Supplier.cs
│ ├── Inventory.cs
│ ├── ShoppingCartItem.cs
│ ├── OrderStatus.cs
│ └── Role.cs
│
├── ViewModels/
│ ├── BaseViewModel.cs
│ ├── MainViewModel.cs
│ ├── LoginViewModel.cs
│ ├── RegisterViewModel.cs
│ ├── StoreViewModel.cs
│ ├── CartViewModel.cs
│ ├── CheckoutViewModel.cs
│ ├── UserProductsViewModel.cs
│ ├── OrderHistoryViewModel.cs
│ ├── SalesHistoryViewModel.cs
│ ├── AdminDashboardViewModel.cs
│ ├── AdminUsersViewModel.cs
│ └── AdminProductsViewModel.cs
│
├── Views/
│ ├── LoginView.xaml
│ ├── RegisterView.xaml
│ ├── StoreView.xaml
│ ├── CartView.xaml
│ ├── CheckoutView.xaml
│ ├── UserProductsView.xaml
│ ├── OrderHistoryView.xaml
│ ├── SalesHistoryView.xaml
│ ├── AdminDashboardView.xaml
│ └── AdminProductsView.xaml
│
├── Services/
│ ├── AuthenticationService.cs
│ └── UserSessionService.cs
│
├── Utilities/
│ ├── RelayCommand.cs
│ ├── RoleTypes.cs
│ └── PasswordBoxHelper.cs
│
├── App.xaml
├── App.xaml.cs
├── MainWindow.xaml
└── RetailDB.sln


---

## 🧠 Componente Cheie

### Models
- Reprezintă tabelele bazei de date
- Generate automat prin **Entity Framework (EDMX)**
- Conțin relații (Navigation Properties)

### ViewModels
- Conțin logica aplicației
- Expun datele către View prin binding
- Gestionează comenzile utilizatorului

### Services
- **AuthenticationService**
  - Login / Register
  - Hash parole (SHA-256)
- **UserSessionService**
  - Gestionare utilizator curent
  - Control stare autentificare

### Utilities
- **RelayCommand** – implementare `ICommand`
- **RoleTypes** – enum roluri
- **PasswordBoxHelper** – binding securizat pentru parole

---

## 🔄 Fluxul Aplicației

1. Pornire aplicație → `LoginView`
2. Autentificare / Înregistrare
3. Navigare magazin
4. Coș → Checkout → Comandă
5. Vizualizare istoric
6. Vânzător:
   - Dashboard produse
   - Comenzi pending
   - Expediere individuală sau completă
7. Admin:
   - Utilizatori
   - Produse
   - Statistici

---

## 🗄️ Baza de Date

- SQL Server LocalDB
- Relații 1:N și N:1
- Status comenzi:
  - `1 = New`
  - `2 = Processed`
  - `3 = Shipped`
- Roluri:
  - `1 = Customer`
  - `2 = Admin`

---

## 🚀 Rulare Proiect

### Cerințe
- Visual Studio 2022+
- .NET Framework 4.7.2+
- SQL Server LocalDB

### Pași
1. Clonează repository-ul:
   ```bash
   git clone <repository-url>
2. Deschide RetailDB.sln

3. Restore NuGet Packages

4. Rulează scriptul SQL (dacă este necesar)

5. Start (F5)

