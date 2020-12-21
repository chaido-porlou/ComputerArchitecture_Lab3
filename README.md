# Αρχιτεκτονική Υπολογιστών

## Εργασία #3

**<u>Εισηγητής</u>:** 	

Παπαευσταθίου Ιωάννης

**<u>Ονόματα</u>:** 	   

Χάιδω Πορλού		

Δημήτριος Παππάς

**<u>ΑΕΜ</u>:**				      

9372						

8391

**<u>Ομάδα:</u>**			

# Αρχιτεκτονική Υπολογιστών

## Εργασία #3

**<u>Εισηγητής</u>:** 	

Παπαευσταθίου Ιωάννης

**<u>Ονόματα</u>:** 	   

Χάιδω Πορλού		

Δημήτριος Παππάς

**<u>ΑΕΜ</u>:**				      

9372						

8391

**<u>Ομάδα:</u>**			

13Α

------

### **ΒΗΜΑ 1**

##### <u>ΕΡΩΤΗΜΑ 1</u>

Το Peak Dynamic (Dynamic Power) είναι η μέγιστη ισχύς που μπορεί να καταναλωθεί από το σύστημα μας και εξαρτάται από τα components του processor. Είναι ανάλογο του συνολικού load capacitance, της τροφοδοσίας, της ενέργειας που καταναλώνεται με το switching των transistor, της συχνότητας ρολογιού και του activity factor.

Το Leakage είναι η ενέργεια που απελευθερώνεται από τα transistor που είναι ανενεργά (off-state), αλλά περνάει κάποιο σχετικά μικρό ρεύμα από αυτά. Χωρίζεται σε Subthreshold Leakage και σε Gate Leakage, που το πρώτο αναφέρεται στην απώλεια ενέργειας λόγω διαρροής ρεύματος από source σε drain, ενώ το δεύτερο αναφέρεται στην απώλεια ενέργειας της πύλη gate του transistor. 

Αν τρέξουμε διαφορετικά προγράμματα σε έναν επεξεργαστή, τότε -στις πληροφορίες του McPAT-  το Leakage αλλά και το Peak Dynamic θα παραμείνουν σταθερά. Ο χρόνος όμως παίζει σημαντικό ρόλο όσον αφορά το Leakage, το οποίο δεν παραμένει σταθερό όταν τον λάβουμε υπόψιν μας. Πιο συγκεκριμένα, όσο περισσότερο χρόνο κάνει ένα πρόγραμμα για να εκτελεστεί, τόσο μεγαλύτερο είναι το Leakage του, καθώς τα off-state transistor συνεχίζουν να έχουν απώλεια ρεύματος για μεγαλύτερο χρονικό διάστημα. Από την άλλη το Peak Dynamic παραμένει σταθερό, διότι εξαρτάται μόνο από από βασικά χαρακτηριστικά του συστήματος (που είναι ίδια κάθε φορά).

##### <u>ΕΡΩΤΗΜΑ 2</u>

Θεωρούμε ότι υπάρχει περίπτωση ο επεξεργαστής που καταναλώνει 40 W να δίνει στο σύστημα μεγαλύτερη διάρκεια μπαταρίας. Αυτό μπορεί να συμβεί αν ο επεξεργαστής αυτός τρέχει πολύ γρηγορότερα σε σχέση με τον πρώτο που καταναλώνει 4 W. Συνέπεια αυτού είναι να έχει μικρότερο συνολικό Leakage, άρα να καταναλώνει και λιγότερη ενέργεια κάθε φορά από την μπαταρία. 

Μπορούμε να αντλήσουμε την παραπάνω πληροφορία από τον McPAT κοιτάζοντας το Total Leakage. Αν αθροίσουμε το Total Leakage και την ενέργεια που καταναλώθηκε (40 ή 4 W), και πολλαπλασιάσουμε το αποτέλεσμα με τον χρόνο, μπορούμε να συμπεράνουμε ποιο είναι το πιο αποδοτικό. Το μικρότερο αποτέλεσμα λοιπόν, μας δίνει και μεγαλύτερη διάρκεια μπαταρίας. Συνεπώς, για να λάβουμε σωστό αποτέλεσμα χρειαζόμαστε και τον χρόνο.

##### <u>ΕΡΩΤΗΜΑ 3</u>

Σύμφωνα με τη βιβλιογραφία ισχύει ότι:

> Runtime Dynamic = Energy Consumption / Time

Υποθέτουμε ότι ο Xeon τρέχει σε χρόνο t, επομένως ο A9 τρέχει σε χρόνο 40t, μιας και είναι 40 φορές πιο αργός. Συνεπώς, το Energy Consumption του Xeon είναι **55.7891** J, ενώ του A9 είναι 40 * 2.96053 = **118.4212** J. Το Leakage του A9 είναι **0.108687** W (**4.34748** J), ενώ του Xeon είναι **36.8319** W (**36.8319** J). Αν λοιπόν, διακοπτόταν η λειτουργία του συστήματος μετά την ολοκλήρωση εκτέλεσης της εφαρμογής, ο Xeon (**92.621** J) θα ήταν πιο energy efficient, έναντι του A9 (**122.76868** J).

Στην περίπτωση όμως που δεν διακοπεί η λειτουργία του Xeon, το Leakage του θα συνεχίσει να αυξάνεται, και με την περάτωση του A9 θα έχει πάρει την τιμή 40 * 36.8319 = **1,473.276** W. Μιλάμε, λοιπόν, για τεράστια αύξηση, κι έτσι ο Xeon δεν υπάρχει περίπτωση να είναι περισσότερο energy efficient.

### **ΒΗΜΑ 2**

##### <u>ΕΡΩΤΗΜΑ 1</u>

Στους παρακάτω πίνακες παραθέτουμε το Power, το Energy (PDP) και το EDP για κάθε benchmark ξεχωριστά. Ο υπολογισμός των προαναφερθέντων έγινε με τους τύπους:

> P = P<sub>dynamic</sub>  + P<sub>leakage</sub> = Runtime Dynamic + Subthreshold Leakage + Gate Leakage (αθροιστικά για core και L2 cache) 

> Energy = Power * Time

> EDP = Energy * Time

Σημείωση: Όπου αναφέρεται το Time, χρησιμοποιήθηκε η τιμή της παραμέτρου sim_seconds από τα αντίστοιχα αρχεία του gem5.

**Benchmark 1: 401.bzip2**

|                             | Power (W)   | Energy (J)  | EDP         |
| --------------------------- | ----------- | ----------- | ----------- |
| L1 CACHE SIZE               |             |             |             |
| L1d=32kB       L1i=64kB     | 1.183972484 | 0.10773676  | 0.009803614 |
| L1d=64kB       L1i=128kB    | 2.071875144 | 0.187838272 | 0.017029606 |
| L1d=128kB       L1i=128kB   | 2.443250724 | 0.213217604 | 0.018607074 |
|                             |             |             |             |
| L2 CACHE SIZE               |             |             |             |
| L2=512kB                    | 1.183972484 | 0.10773676  | 0.009803614 |
| L2=1024kB                   | 1.190919595 | 0.105695305 | 0.009380564 |
| L2=2048kB                   | 1.156548217 | 0.146797196 | 0.018632528 |
| L2=4096kB                   | 1.21376885  | 0.103331784 | 0.008796945 |
|                             |             |             |             |
| CACHE ASSOCIATIVITY         |             |             |             |
| L1  assoc=1     L2 assoc=2  | 1.183972484 | 0.10773676  | 0.009803614 |
| L1  assoc=2     L2 assoc=4  | 1.194704087 | 0.107093274 | 0.009599841 |
| L1  assoc=4     L2 assoc=8  | 1.126858665 | 0.100103363 | 0.008892582 |
| L1  assoc=8     L2 assoc=16 | 1.295780094 | 0.114570284 | 0.010130075 |
|                             |             |             |             |
| CACHE LINE SIZE             |             |             |             |
| cache line=32               | 0.858091364 | 0.086179832 | 0.008655213 |
| cache line = 64             | 1.183972484 | 0.10773676  | 0.009803614 |
| cache line = 128            | 1.23604696  | 0.112061253 | 0.010159585 |

**Benchmark 2: 429.mcf**

|                             | Power (W)   | Energy (J)  | EDP         |
| :-------------------------- | ----------- | ----------- | ----------- |
| L1 CACHE SIZE               |             |             |             |
| L1d=32kB       L1i=64kB     | 1.216605044 | 0.070362353 | 0.004069407 |
| L1d=64kB       L1i=128kB    | 2.116837144 | 0.119916707 | 0.006793162 |
| L1d=128kB       L1i=128kB   | 2.490743157 | 0.143695954 | 0.008290107 |
|                             |             |             |             |
| L2 CACHE SIZE               |             |             |             |
| L2=512kB                    | 1.216605044 | 0.070362353 | 0.004069407 |
| L2=1024kB                   | 1.218828885 | 0.070292299 | 0.004053897 |
| L2=2048kB                   | 1.221887583 | 0.070240208 | 0.004037758 |
| L2=4096kB                   | 1.2272927   | 0.07052883  | 0.00405308  |
|                             |             |             |             |
| CACHE ASSOCIATIVITY         |             |             |             |
| L1  assoc=1     L2 assoc=2  | 1.216605044 | 0.070362353 | 0.004069407 |
| L1  assoc=2     L2 assoc=4  | 1.226866178 | 0.070749692 | 0.004079922 |
| L1  assoc=4     L2 assoc=8  | 1.184126553 | 0.068256607 | 0.003934516 |
| L1  assoc=8     L2 assoc=16 | 2.77730279  | 0.160078178 | 0.009226586 |
|                             |             |             |             |
| CACHE LINE SIZE             |             |             |             |
| cache line=32               | 0.899934005 | 0.052963816 | 0.003117079 |
| cache line = 64             | 1.216605044 | 0.070362353 | 0.004069407 |
| cache line = 128            | 1.21433608  | 0.068790925 | 0.003896937 |

**Benchmark 3: 458.sjeng**

|                             | Power (W)   | Energy (J)  | EDP         |
| --------------------------- | ----------- | ----------- | ----------- |
| L1 CACHE SIZE               |             |             |             |
| L1d=32kB       L1i=64kB     | 1.140443694 | 0.586263328 | 0.301378044 |
| L1d=64kB       L1i=128kB    | 1.891806384 | 0.972494423 | 0.256985124 |
| L1d=128kB       L1i=128kB   | 2.204101284 | 1.132949938 | 0.299342971 |
|                             |             |             |             |
| L2 CACHE SIZE               |             |             |             |
| L2=512kB                    | 1.140443694 | 0.586263328 | 0.301378044 |
| L2=1024kB                   | 1.143849995 | 0.587954911 | 0.302074771 |
| L2=2048kB                   | 1.148881253 | 0.590263019 | 0.303260612 |
| L2=4096kB                   | 1.15666255  | 0.593971666 | 0.305017518 |
|                             |             |             |             |
| CACHE ASSOCIATIVITY         |             |             |             |
| L1  assoc=1     L2 assoc=2  | 1.140443694 | 0.586263328 | 0.301378044 |
| L1  assoc=2     L2 assoc=4  | 1.144388977 | 0.588238822 | 0.302366519 |
| L1  assoc=4     L2 assoc=8  | 1.013223405 | 0.52079683  | 0.267689571 |
| L1  assoc=8     L2 assoc=16 | 1.109170884 | 0.570082778 | 0.293006585 |
|                             |             |             |             |
| CACHE LINE SIZE             |             |             |             |
| cache line=32               | 0.814942404 | 0.719179337 | 0.634669292 |
| cache line = 64             | 1.140443694 | 0.586263328 | 0.301378044 |
| cache line = 128            | 1.16209266  | 0.3957309   | 0.13475943  |

**Benchmark 4: 470.lbm**

|                             | power (W)   | energy (J)  | EDP         |
| --------------------------- | ----------- | ----------- | ----------- |
| L1 CACHE SIZE               |             |             |             |
| L1d=32kB       L1i=64kB     | 1.153494474 | 0.203529486 | 0.035911964 |
| L1d=64kB       L1i=128kB    | 1.940783894 | 0.340964678 | 0.059902038 |
| L1d=128kB       L1i=128kB   | 2.265984184 | 0.397582787 | 0.069758683 |
|                             |             |             |             |
| L2 CACHE SIZE               |             |             |             |
| L2=512kB                    | 1.153494474 | 0.203529486 | 0.035911964 |
| L2=1024kB                   | 1.156657705 | 0.203586793 | 0.035833922 |
| L2=2048kB                   | 1.161289553 | 0.204282445 | 0.035935325 |
| L2=4096kB                   | 1.16870125  | 0.20533146  | 0.036075095 |
|                             |             |             |             |
| CACHE ASSOCIATIVITY         |             |             |             |
| L1  assoc=1     L2 assoc=2  | 1.153494474 | 0.203529486 | 0.035911964 |
| L1  assoc=2     L2 assoc=4  | 1.160154287 | 0.202933028 | 0.035496842 |
| L1  assoc=4     L2 assoc=8  | 1.032957375 | 0.180683871 | 0.031605042 |
| L1  assoc=8     L2 assoc=16 | 1.149682624 | 0.20155316  | 0.035334688 |
|                             |             |             |             |
| CACHE LINE SIZE             |             |             |             |
| cache line=32               | 0.824615224 | 0.231600607 | 0.065047115 |
| cache line = 64             | 1.153494474 | 0.203529486 | 0.035911964 |
| cache line = 128            | 1.17483646  | 0.15412562  | 0.020219586 |

Στη συνέχεια παραθέτουμε 4 διαγράμματα για το Energy - Delay Product σε κάθε περίπτωση, από τα οποία θα βγάλουμε και τα τελικά μας συμπεράσματα.

**Benchmark 1: 401.bzip2**

[![bzip-edp.png](https://i.postimg.cc/rFWQdJLx/bzip-edp.png)](https://postimg.cc/0bkpF7jy)

**Benchmark 2: 429.mcf**

[![mcf-edp.png](https://i.postimg.cc/vBJ5MJTj/mcf-edp.png)](https://postimg.cc/k6y2vhxF)

**Benchmark 3: 458.sjeng**

[![sjeng-edp.png](https://i.postimg.cc/XYcL3JnS/sjeng-edp.png)](https://postimg.cc/DS0LP7WB)

**Benchmark 4: 470.lbm**

[![libm-edp.png](https://i.postimg.cc/TYxQsgXq/libm-edp.png)](https://postimg.cc/8syhJFcj)

Από τα παραπάνω αποτελέσματα, καταλήγουμε σε συμπεράσματα για τη βελτιστοποίηση γινομένου Energy - Delay, η οποία συμβαίνει όταν έχουμε το μικρότερο EDP. Έτσι, η καλύτερη επιλογή για κάθε benchmark αναλύεται στον παρακάτω πίνακα (καθώς και η πραγματική τιμή του EDP που βρήκαμε μετά από αντίστοιχη εκτέλεση).

|           | L1 dcache - L1 icache | L2 cache | L1i - L1d - L2 Associativity | Cache Line Size |     EDP      |
| :-------: | :-------------------: | :------: | :--------------------------: | :-------------: | :----------: |
| 401.bzip2 |      32kB - 64kB      |  4096kB  |          4 - 4 - 8           |       32B       | 0.0074254720 |
|  429.mcf  |      32kB - 64kB      |  2048kB  |          4 - 4 - 8           |       32B       | 0.0030452460 |
| 458.sjeng |      32kB - 64kB      |  512kB   |          1 - 1 - 2           |      128B       |  0.13475943  |
|  470.lbm  |      32kB - 64kB      |  512kB   |          1 - 1 - 2           |      128B       | 0.020219586  |

##### <u>ΕΡΩΤΗΜΑ 2</u>

Παρουσιάζουμε παρακάτω τα διαγράμματα που δείχνουν την επίδραση της αλλαγής διαφόρων παραμέτρων (όπως επιλέξαμε στην εργασία 2) στο Peak Power αλλά και στο Area.

##### PEAK POWER

Υπολογίσαμε το peak power για κάθε περίπτωση αθροίζοντας τα δεδομένα για το core και την L2 cache, σύμφωνα με τον παρακάτω τύπο:

> Peak Power = (Peak Dynamic + Subthreshold Leakage + Gate Leakage)<sub>core</sub> + (Peak Dynamic + Subthreshold Leakage + Gate Leakage)<sub>L2</sub>

[![L1-POWER.png](https://i.postimg.cc/QMz014xq/L1-POWER.png)](https://postimg.cc/WDMGP7ZD)

[![L2-POWER.png](https://i.postimg.cc/L6VDN685/L2-POWER.png)](https://postimg.cc/JGGjh8JC)

[![ASSOCIATIVITY-POWER.png](https://i.postimg.cc/prJfGqx4/ASSOCIATIVITY-POWER.png)](https://postimg.cc/PvNvNbCQ)

[![CACHE-LINE-SIZE-POWER.png](https://i.postimg.cc/6Q4dJ9td/CACHE-LINE-SIZE-POWER.png)](https://postimg.cc/cKZKfGKH)

##### AREA

[![L1-AREA.png](https://i.postimg.cc/SRk8MC8r/L1-AREA.png)](https://postimg.cc/8JXj8FZJ)

[![L2-AREA.png](https://i.postimg.cc/MpvBVWch/L2-AREA.png)](https://postimg.cc/CRpdVpsN)

[![ASSOCIATIVITY-AREA.png](https://i.postimg.cc/TYHLRZkQ/ASSOCIATIVITY-AREA.png)](https://postimg.cc/SJCNdtbz)

[![CACHE-LINE-SIZE-AREA.png](https://i.postimg.cc/mgvP97WH/CACHE-LINE-SIZE-AREA.png)](https://postimg.cc/LJV4KYX9)

---

Ολοκληρώνοντας την ανάλυσή μας, καθώς και τον κύκλο των εργαστηρίων, θα θέλαμε να παρουσιάσουμε πιθανούς λόγους για τους οποίους τα αποτελέσματα που προέρχονται από τα διάφορα simulations μπορεί να μην είναι και τόσο αξιόπιστα, ή να υπάρχει αυξημένος βαθμός σφάλματος. Πιο συγκεκριμένα, παραθέτουμε παρακάτω συνοπτικά κάποιες πιθανές αιτίες για τις παραπάνω αποκλίσεις.

Όσον αφορά το McPAT, κάποιοι λόγοι είναι οι εξής:

- **Incomplete/missing models**

Υπάρχει μεγάλη πιθανότητα τα μοντέλα που προσομοιώνονται με το McPAT να είναι μη ολοκληρωμένα. Χρησιμοποιώντας και τη βιβλιογραφία, διαπιστώσαμε πως κάποια **macros δεν μοντελοποιούνται**, με αποτέλεσμα να μην υπολογίζονται στο συνολικό power consumption.  Συνεπώς, θα πρέπει να θεωρείται ως μέγιστη τιμή στην μοντελοποίηση πραγματικών συστημάτων η τιμή που δίνεται από τον εξομοιωτή, καθώς ήδη έχει παραβλέψει ένα τμήμα του power consumed.

- **Insufficient modeling detail**

Θεωρήσαμε σαν πρώτη σκέψη πως ο εξομοιωτής μπορεί να χρησιμοποιεί **περισσότερους πόρους** από όσους είναι ακριβώς απαραίτητοι για την εκτέλεση μιας διεργασίας, για χάρη απλότητας. Διαβάζοντας τα σχετικά papers, διαπιστώνουμε πως ως ένα βαθμό το σκεπτικό ισχύει, καθώς το McPAT δεσμεύει **διπλάσια read/write ports** κάθε φορά, ανεξαρτήτως της εντολής. Υποθέτουμε πως το παραπάνω συμβαίνει για να απλουστευθεί η διαδικασία.

Επιπροσθέτως, το McPAT θεωρεί το **clock-gating και το data-gating τέλειο**. Τις περισσότερες φορές αυτό ισχύει, αλλά υπάρχει πιθανότητα λόγω σχεδιαστικής πολυπλοκότητας ή λόγων χρονισμού να μην υπάρχει μηδενική κατανάλωση dynamic power (όπως συμβαίνει με τέλειο clock- και data-gating). Συνεπώς, και σε αυτή την περίπτωση, **το τελικό power consumption που παρουσιάζεται είναι μικρότερο από το πραγματικό**.

- **Modeling assumption errors**

Μία τελευταία σκέψη που κάναμε είναι ότι η αρχιτεκτονική που προσπαθεί να εξομοιώσει ο το McPAT δεν είναι ακριβώς ίδια με την αρχιτεκτονική μίας πραγματικής CPU. Ο εξομοιωτής κάνει δηλαδή κάποιες **εικασίες όσον αφορά το hardware**, όπως για παράδειγμα το ποια structures είναι shared ή duplicated. Επίσης, επειδή **οι λογικές και αριθμητικές μονάδες είναι δύσκολο να μοντελοποιηθούν** ειδικά σε επίπεδο αρχιτεκτονικής, χρησιμοποιούνται ήδη **προϋπάρχοντα data sets** ώστε να υπολογισθούν τα αποτελέσματα τους εμπειρικά.

**~**

Τέλος, η χρήση δύο διαφορετικών προγραμμάτων είναι πολύ πιθανό να οδηγεί σε επιπλέον σφάλματα. Μια υπόθεση είναι πως ο κάθε εξομοιωτής κάνει διαφορετικά assumptions όσον αφορά την αρχιτεκτονική και τον τρόπο λειτουργίας ενός συστήματος, που μπορεί να είναι αντικρουόμενα. Το αποτέλεσμα λοιπόν μπορεί να έχει ακόμα μεγαλύτερο βαθμό σφάλματος, σε σχέση με μεμονωμένες εξομοιώσεις. Θεωρήσαμε επίσης ότι μπορεί να υπάρχουν σφάλματα στρογγυλοποίησης, τα οποία εντείνονται αν περάσουν από πολλαπλούς υπολογισμούς. 

---

#### ΒΙΒΛΙΟΓΡΑΦΙΑ

[https://www.samxi.org/papers/xi_hpca2015.pdf](https://www.samxi.org/papers/xi_hpca2015.pdf)

[https://upcommons.upc.edu/bitstream/handle/2117/77219/108862.pdf?sequence=1&isAllowed=y](https://upcommons.upc.edu/bitstream/handle/2117/77219/108862.pdf?sequence=1&isAllowed=y)

[http://users.ece.utexas.edu/~ljohn/teaching/382m-15/lectures/lec16.pdf](http://users.ece.utexas.edu/~ljohn/teaching/382m-15/lectures/lec16.pdf)

[http://www.es.mdh.se/pdf_publications/2273.pdf](http://www.es.mdh.se/pdf_publications/2273.pdf)

[http://www.eecs.umich.edu/courses/eecs470/OLD/w14/lectures/470L14W14.pdf](http://www.eecs.umich.edu/courses/eecs470/OLD/w14/lectures/470L14W14.pdf)

[https://www.hpl.hp.com/research/mcpat/micro09.pdf](https://www.hpl.hp.com/research/mcpat/micro09.pdf)

[https://research.cs.wisc.edu/vertical/papers/2014/wddd-sim-harmful.pdf](https://research.cs.wisc.edu/vertical/papers/2014/wddd-sim-harmful.pdf)

[https://ieeexplore.ieee.org/document/7056064?denied=](https://ieeexplore.ieee.org/document/7056064?denied=)

---

#### ΚΡΙΤΙΚΗ

Από την παραπάνω εργασία μάθαμε πως μπορούμε να εξομοιώσουμε αποτελέσματα όσον αφορά το power και την κατανάλωση ενέργειας σε ένα σύστημα (ανάλογα με το πρόγραμμα που εκτελείται), μέσω του emulator McPAT, το οποίο μοντελοποιεί αρχιτεκτονικές επεξεργαστών και παρέχει εκτιμήσεις για τα παραπάνω. Το πρόγραμμα McPAT δίνει πληροφορίες συνοπτικά ή αναλυτικά, ανάλογα με το τι αναζητά ο χρήστης. 

Πιο συγκεκριμένα, μας δίνει πληροφορίες για το Leakage αλλά και για το Peak Dynamic Power, καθώς και για το μέγεθος του Area, τόσο για ολόκληρο το σύστημα όσο και για κάθε component ξεχωριστά. Χρησιμοποιώντας τις πληροφορίες αυτές, μπορέσαμε να εξάγουμε συμπεράσματα για το ποια συστήματα είναι πιο energy efficient και γιατί, και μπήκαμε στη διαδικασία να συγκρίνουμε ενεργειακά επεξεργαστές με διαφορετικά χαρακτηριστικά. 

Πειραματιστήκαμε με τον συνδυασμό gem5 και McPAT ώστε να βρούμε το βέλτιστο Energy - Delay Product όσον αφορά τα benchmarks που είχαμε χρησιμοποιήσει στην προηγούμενη άσκηση. Τέλος, αναζητήσαμε στη βιβλιογραφία λόγους για τους οποίους δημιουργούνται προβλήματα και παρουσιάζονται σφάλματα μέσω αυτής της διαδικασίας, και τους παρουσιάσαμε σε συνδυασμό με τις δικές μας σκέψεις. 

Ένας προβληματισμός μας ήταν πως στα ερωτήματα 1 & 3 (βήμα 1), δεχόμασταν κάποια αποτελέσματα από τον McPAT τα οποία δεν μπορούσαμε να αποκωδικοποιήσουμε όσον αφορά την προέλευσή τους. Δηλαδή από την εκτέλεση ποιας διεργασίας προέκυπτε το Leakage και το Runtime Dynamic (αναφέρεται σε κάποιο παράδειγμα;).

Επίσης, όσον αφορά το βήμα 2 και το EDP, αναφέρεται πως για τον υπολογισμό του θα χρησιμοποιηθεί και το Area, το οποίο θεωρούμε πως δε χρειάζεται. Μπερδεύει δηλαδή περισσότερο η παρουσία του. Αν αυτό που ζητείται είναι διαγράμματα συναρτήσει αυτού, θα έπρεπε να παρατίθεται σαν ξεχωριστό ερώτημα.

Σημείωση 1: Και σε αυτή την εργασία (όπως και στη 2η), υλοποιήθηκαν μόνο τα 4 από τα 5 benchmark, διότι το hmmer είχε πρόβλημα στην εκτέλεση του στον gem5, και χωρίς αποτελέσματα δε μπορούσαμε να συνεχίσουμε στο McPAT. Παρόλη τη συνεννόηση με τον υπεύθυνο, δε μπόρεσε να βρεθεί λύση στο error.

Σημείωση  2: Το script read_results.sh δημιούργησε πρόβλημα στο διάβασμα των αποτελεσμάτων με παρόμοια ονόματα (πχ bzip_1 & bzip_11 καθώς και libm_1 & libm_10), με αποτέλεσμα να πάρουμε κάποιες λάθος μετρήσεις στην εργασία 2. Υποθέτουμε ότι έχει κάποιο θέμα το script (δεν τον διαβάσαμε διότι θεωρήσαμε πως είναι σωστό καθώς μας το δίνετε έτοιμο).

------

#### FOLDER STRUCTURE

```
.
├── McPAT_results		#McPAT results for all benchmarks
│   ├── bzip2
|   ├── libm
|   ├── mcf
│   └── sjeng
├── Time_results		#time and cpi results for all benchmarks (gem5)					
│   ├── Results_bzip2.txt
|   ├── Results_libm.txt
|   ├── Results_mcf.txt
│   └── Results_sjeng.txt
├── PEAK POWER-AREA.xlsx		#xlsx file with peak power & area matrices
├── POWER-ENERGY-EDP.xlsx		#xlsx file with calculated power, energy & EDP           
└── README.md             
```

