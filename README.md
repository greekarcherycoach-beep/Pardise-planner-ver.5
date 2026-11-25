# Paradise Park Wizard – APK & portable EXE

Δομή:

- `mobile/www/index.html` → η mobile έκδοση (γίνεται Android APK με Capacitor)
- `desktop/index.html` → η desktop έκδοση (γίνεται portable EXE για Windows 10/11 με Electron)
- `.github/workflows/android.yml` και `windows.yml` → αυτόματο build στο GitHub

## Βήματα

1. Φτιάξτε νέο repository στο GitHub και ανεβάστε **όλο** αυτό το περιεχόμενο (συμπεριλαμβανομένου του φακέλου `.github`) στο branch `main`.
2. Πηγαίνετε στην καρτέλα **Actions**. Τα δύο workflows τρέχουν αυτόματα σε κάθε push (ή χειροκίνητα με «Run workflow»).
3. Όταν τελειώσουν (3–8 λεπτά), ανοίξτε το run και κατεβάστε από το **Artifacts**:
   - `Paradise-Park-Wizard-apk` → `app-debug.apk`
   - `Paradise-Park-Wizard-portable-exe` → `Paradise-Park-Wizard-portable.exe`

## Σημειώσεις

- Το APK είναι *debug-signed*: εγκαθίσταται κανονικά σε Android (επιτρέψτε «εγκατάσταση από άγνωστες πηγές»). Για Google Play χρειάζεται release build με δικό σας keystore.
- Το EXE είναι portable: δεν χρειάζεται εγκατάσταση, τρέχει με διπλό κλικ. Τα δεδομένα αποθηκεύονται τοπικά στο προφίλ του χρήστη των Windows. Το Windows SmartScreen μπορεί να δείξει προειδοποίηση επειδή το αρχείο δεν είναι υπογεγραμμένο («Περισσότερες πληροφορίες → Εκτέλεση ούτως ή άλλως»).
- Στο Android η «Αποθήκευση/Excel» και η «Εκτύπωση» ανοίγουν το παράθυρο κοινοποίησης του κινητού (Drive, Αρχεία, Viber, e-mail κ.λπ.), μέσω των plugins Filesystem και Share του Capacitor που εγκαθίστανται αυτόματα από το `package.json`. Η «Εκτύπωση» στέλνει ένα αρχείο HTML· ανοίξτε το στον browser και επιλέξτε Εκτύπωση / Αποθήκευση ως PDF.
- Για να ενημερώσετε την εφαρμογή, αντικαταστήστε τα `index.html` και κάντε push.
