**Tasca 01\. Analitzar necessitats clients**

**1\. Optimització del Flux de Treball:**

- **Dissenyar com passarem de la comanda manual a la digital (comandes des de taula, comandes de mà o TPV central?).**  
- **Establir com es comunicarà la barra amb la cuina/zona de preparació (impressores de tiquets o pantalles de cuina?).**

El flux d'una comanda segueix cinc grans etapes:

**1\. Acollida**: El client seu a taula o s'acosta al taulell. El cambrer l'atén amb una tablet o es fa servir el TPV central si és una barra ràpida.

**2\. Comanda digital**: La comanda s'introdueix al sistema POS. En el mateix instant, el sistema descompta l'estoc, registra l'hora i la taula i transmet l'ordre a cuina per la xarxa interna.

**3\. Producció**: La cuina o la barra rep la comanda en una pantalla o via impressora tèrmica. Marca el plat o la beguda com a llest quan acaba.

**4\. Servei**: El cambrer rep l'avís a la seva tablet, recull el producte i el porta a la taula. Si es cau, el client demana el compte.

**5\. Cobrament**: El cambrer envia el compte al TPV. El client paga i el sistema genera el tiquet, tanca la comanda i actualitza l'informe de vendes en temps real.

**2\. Infraestructura de Xarxa i WiFi Social:**

- **Crear una xarxa segura. Els clients volen WiFi per teletreballar, però el sistema de cobrament ha d'anar per una xarxa aïllada.**  
- **Valorar l'ús d'un Portal Captiu (on el client hagi d'acceptar condicions o veure una promoció abans de connectar-se).**

### **Principi fonamental: separació total per VLAN**

|  | VLAN 10 — Staff | VLAN 20 — Clients |
| ----- | ----- | ----- |
| **Ús** | TPV, datàfon, tablets, impressores | Smartphones i portàtils dels clients |
| **Accés a Internet** | Sí, sense restriccions | Sí, limitat a 10 Mbps per usuari |
| **Accés entre VLANs** | Bloquejat per firewall | Bloquejat per firewall |
| **Autenticació** | Contrasenya WPA3 interna | Portal Captiu (acceptació de T\&C) |
| **SSID** | RacoStaff\_5GHz (ocult) | RacoCafe\_WiFi (visible) |

### **Portal Captiu**

Quan un client es connecta al WiFi, veu una pàgina de benvinguda amb el logo de la cafeteria, la promoció del dia, el formulari d'acceptació de condicions i opcionalment, un camp d'email per a fidelització. 

**El logo que sortiria a la pàgina web seria aquest:**

<img width="237" height="207" alt="image" src="https://github.com/user-attachments/assets/c6283fa7-6895-43ce-b53a-374503c117d3" />

<img width="536" height="354" alt="image" src="https://github.com/user-attachments/assets/3230c82e-fa17-4d22-be2a-21790a13bcee" />

## **3\. Pressupost de Hardware**

### **3.1 Punt de Venda (TPV)**

| Article | Model recomanat | Preu aprox. amb IVA incluit |
| ----- | ----- | ----- |
| TPV tàctil 15p. IP54 | Elo PayPoint Plus / Sunmi T2 | 480 \- 650 € |
| Calaix portamonedes | APG Vasario 16x16 | 85 \- 110 € |
| Impressora tèrmica taulell | Epson TM-T88VII | 220 \- 280 € |
| **Subtotal TPV** |  | **850 \- 1.040 €** |

### **3.2 Mobilitat (cambrer)**

| Article | Model recomanat | Preu aprox. amb IVA incluit |
| ----- | ----- | ----- |
| Tablet 8p. robusta | Lenovo Tab M8 (4a gen) \+ funda | 160 \- 200 € |
| (Alternativa) Smartphone | Samsung Galaxy XCover 6 Pro | 350 € |
| **Subtotal x1 dispositiu** |  | **160 \- 350 €** |

Per a una cafeteria amb 2 \- 3 cambrers, preveure 2 tablets: 320 \- 400 € addicionals.

### **3.3 Impressora de Cuina**

| Article | Model recomanat | Preu aprox. amb IVA incluit |
| ----- | ----- | ----- |
| Impressora tèrmica cuina | Epson TM-T20III (IP54) | 190 \- 240 € |
| *(Alternativa KDS)* Pantalla cuina | Orderman KDS 10" | 320 \- 450 € |

### **3.4 Xarxa**

| Article | Model recomanat | Preu aprox. amb IVA incluit |
| ----- | ----- | ----- |
| Router / Firewall | Ubiquiti UniFi Dream Machine SE | 380 \- 420 € |
| Punt d'Accés WiFi 6 (x2) | Ubiquiti UniFi U6 Lite | 100 € / unitat \- **200 €** |
| Switch gestionable 8p | Ubiquiti UniFi USW-8-PoE | 140 \- 160 € |
| Cablatge Cat6 \+ instal·lació |  | 150 \- 250 € |
| **Subtotal xarxa** |  | **870 \- 1.030 €** |

### **Resum pressupost hardware total**

| Bloc | Cost estimat |
| ----- | ----- |
| TPV \+ calaix \+ impressora taulell | 850 \- 1.040 € |
| Tablets cambrers (x2) | 320 \- 400 € |
| Impressora cuina | 190 \- 240 € |
| Infraestructura de xarxa | 870 \- 1.030 € |
| **TOTAL** | **2.230 \- 2.710 €** |

## 

## 

## 

## **4\. Informe de Software: Comparativa de Costos**

### **Opcions avaluades**

**Opció A:  Software Lliure:** Floreant POS (Java, llicència GPL) \+ Odoo Community 17 per a estoc i informes. Allotjament en un mini-PC local (Intel NUC, 250 €) o VPS bàsic (8 €/mes).

**Opció B:  Software Comercial:** Revo XEF (especialitzat en restauració, SAAS). Inclou POS, gestió de taules, estoc bàsic, informes i suport tècnic.

### **Comparativa de costos (sense hardware)**

| Concepte | Opció A (Lliure) | Opció B (Revo XEF) |
| ----- | ----- | ----- |
| Llicència programari | 0 € | 0 € |
| Quota mensual | 8 €/mes (VPS) | 59 €/mes |
| Implementació/configuració | 400 – 800 € | 0 – 150 € |
| Formació | 4–8 h  | Inclosa al pla |
| Manteniment anual | 0 €  | Inclòs |
| Integracions (datàfon, etc.) | Manual o desenvolupament | Incloses (Adyen, SumUp…) |

### **Projecció de costos totals (software únicament)**

| Període | Opció A (Lliure) | Opció B (Revo XEF) |
| ----- | ----- | ----- |
| Any 1 | 600 – 1.000 € | 708 – 858 € |
| Any 2 | 96 € | 708 € |
| Any 3 | 96 € | 708 € |
| **Total 3 anys** | **792 – 1.192 €** | **2.124 – 2.274 €** |

### **Conclusió recomanada**

A curt termini, els costos són similars. A llarg termini, l'opció lliure és 1.300 € més econòmica, però requereix un responsable tècnic intern o contracte de manteniment. Per a un negoci sense personal IT dedicat, Revo XEF ofereix una relació qualitat-preu excel·lent: interfície intuïtiva, actualizaciones automàtiques, suport en català i castellà i integracions de pagament natives.

## 

## **5\. Pla de Contingència**

### **Escenari A: Cau el WiFi intern**

| Risc | Impacte | Acció |
| ----- | ----- | ----- |
| TPV perd connexió al servidor | Alt | El software POS funciona en mode offline local: les comandes es desen al disc del TPV i es sincronitzen quan torna la xarxa. |
| Tablets cambrers desconnectades | Mitjà | **Comanda paper**  fins a recuperar la xarxa |
| Impressora cuina sense xarxa | Baix | Alternativa verbal o WhatsApp intern. |

### **Escenari B: Cau Internet (ISP)**

| Risc | Impacte | Acció |
| ----- | ----- | ----- |
| Cobrament amb targeta | Alt | El **datàfon amb SIM 4G pròpia** opera independent del WiFi. Sempre funciona. |
| Actualització d'estoc | Baix | Es difereix. Es sincronitza quan torna la connexió |
| WiFi clients no disponible | Nul (per al negoci) | Es pot informar amb un cartell. No afecta les vendes |

### **Escenari C: Fallada total del hardware TPV**

| Risc | Impacte | Acció |
| ----- | ----- | ----- |
| TPV principal inutilitzable | Alt | **Pla de backup:** instal·lar el POS en una tablet de reserva. Temps de recuperació més de 5 minuts. |
| Calaix portamonedes bloquejat | Baix | El calaix disposa d'obertura mecànica manual amb cla. |

### 

### **Mesures preventives generals**

- **UPS (SAI)** per al router i el switch: protegeix de talls de llum breus (30 min). Model recomanat: APC Back-UPS 700VA (80 €).  
- **Còpia de seguretat diària** automàtica al núvol.  
- **Documentació operativa laminada** al taulell. Com cobrar manualment, com obrir el calaix, contacte del suport tècnic.  
- **Revisió trimestral** de l'estat de la xarxa i actualitzacions de firmware dels APs.
