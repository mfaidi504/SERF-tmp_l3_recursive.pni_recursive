# SERF-tmp_l3_recursive.pni_recursive


![SERF1](foto10.png)



# Fiber Network Architecture – Key Concepts (Open Fiber)

This document explains some fundamental concepts used in **FTTH (Fiber To The Home)** networks, particularly those used by companies such as Open Fiber in Italy.

---

# 1. What is FTTH?

**FTTH (Fiber To The Home)** is a broadband network architecture where **optical fiber cables run directly from the provider’s infrastructure to the user's home**.

Compared to copper networks, FTTH provides:

* Higher bandwidth
* Lower latency
* Better reliability
* Future scalability

FTTH is widely used to support modern services such as:

* Ultra-HD video streaming
* Cloud services
* Online gaming
* Internet of Things (IoT)
* 5G mobile backhaul

---

# 2. PON Technology

Most FTTH networks use **PON (Passive Optical Network)** technology.

PON allows a **single optical fiber from the provider to be shared by multiple users**.

This architecture is called:

**Point-to-Multipoint**

Instead of providing a dedicated fiber to every user, the signal is split using passive devices.

### How it works

Provider Central Office
↓
Fiber Cable
↓
Optical Splitter
↓
Multiple Homes

The splitter divides the optical signal to serve many customers.

---

# 3. Evolution of PON Technologies

PON technology continues to evolve to provide higher speeds.

| Technology | Download Speed | Upload Speed  |
| ---------- | -------------- | ------------- |
| GPON       | 2.5 Gbps       | 1.25 Gbps     |
| XG-PON     | 10 Gbps        | 2.5 Gbps      |
| XGS-PON    | 10 Gbps        | 10 Gbps       |
| NG-PON2    | up to 40 Gbps  | multi-channel |

This evolution allows networks to support increasing bandwidth demands.

---

# 4. PON vs AON

Two main fiber network architectures exist.

## Passive Optical Network (PON)

Characteristics:

* Point-to-Multipoint
* Uses passive components (splitters)
* No electrical power required along the path
* Lower deployment cost
* Lower failure probability

This is the architecture used by many providers.

---

## Active Optical Network (AON)

Characteristics:

* Point-to-Point architecture
* Each user has a dedicated fiber
* Requires active equipment (switches, routers)
* Requires electrical power along the network
* Higher deployment cost

Although AON offers dedicated connections, it is more expensive to deploy.

---

# 5. Apparato Edificio (Building Equipment)

**Apparato Edificio** refers to the **fiber distribution equipment installed inside a building**.

Its purpose is to **connect the building's apartments to the fiber network coming from the street**.

### Typical location

The equipment is usually installed in:

* Building entrance
* Technical room
* Electrical room
* Basement

### Function

The Apparato Edificio distributes the incoming fiber to each apartment.

Network flow example:

Street Fiber Network
↓
Building Equipment (Apparato Edificio)
↓
Fiber cable to each apartment
↓
Router / ONT inside the home

### Components typically inside

The building equipment may contain:

* Optical splitter
* Fiber connectors
* Patch panel
* Distribution ports for apartments

For example:

If a building has **10 apartments**, a fiber connection arrives from the street and is distributed to all apartments through this device.

---

# 6. Common FTTH Network Elements

Several components are commonly used in FTTH infrastructures.

| Component | Description                          |
| --------- | ------------------------------------ |
| POP       | Point of Presence – main network hub |
| PFS       | Street distribution node             |
| PTE       | Building fiber distribution box      |
| PTO       | Optical outlet inside the apartment  |

These elements create the path from the operator’s network to the final user.

---

# 7. Transport Network

Once data enters the operator's network, it is transported through a national infrastructure composed of two main layers.

### Core Network (Backbone)

* Connects major cities
* High-capacity optical links
* Supports large volumes of traffic

### Aggregation Network

* Collects traffic from access networks
* Connects local areas to the backbone

---

# 8. Optical Transport Technologies

Modern fiber networks use technologies such as:

**DWDM (Dense Wavelength Division Multiplexing)**

This allows multiple optical signals to travel on the same fiber using different wavelengths.

Benefits:

* Massive capacity
* Efficient fiber utilization
* Terabit-scale transmission

A single fiber can carry hundreds of gigabits per second.

---

# 9. Future Applications

High-capacity fiber networks enable future digital services including:

* 8K video streaming
* Virtual Reality (VR)
* Augmented Reality (AR)
* Cloud gaming
* Autonomous vehicles
* Smart cities
* Internet of Things (IoT)

---

# Conclusion

FTTH networks represent the future of broadband connectivity.

Using technologies like **PON**, operators can deliver high-speed internet to millions of users efficiently and at lower cost.

Infrastructure elements such as **Apparato Edificio** play a crucial role in distributing fiber connections within residential buildings, ensuring that each apartment can access ultra-broadband services.




![SERF2](foto5.png)

03_016_016024_8000032933_8

APPARATO EDIFICIO :4026609553665681626

because Scala a lot of number select : select filter Commune : Bergamo QLIK -> NETWORK CREATION STREAM -> DASHBOARD CIVILE NORD-OVEST BECUAE BERGAMO THERE

Down there are a lot of columns. We need to focus and go inside the sheet column SCALA SHEET and make zoom on the map so the value of the SCALA SHEET column shows


![SERF3](foto6.png)
![SERF4](foto7.png)



APPARATO EDIFICIO :4026609553665681626

SELECT * FROM tmp_l3_recursive.pni_recursive where id = xxxx --PATH_id LIKE '%3212379411477711925%' LIMIT 100 ;

SELECT id,path_id FROM tmp_l3_recursive.pni_recursive WHERE id = '4026609553665681626';

instead of xxxx try to use the code of apparato edificio you will see the list of cable from apparato edificio to pop this is an usefull table to check the continuity of the net what he means




# Open Fiber Network FAQ / Notes

This document summarizes key concepts about network elements and length calculation in the Open Fiber network, as well as notes on potential visualization issues.

---

## 1. Network Length Calculation

**Question:**  
When calculating the network length, should it be measured from the user’s home to the POP, or from the Building Apparatus to the POP?

**Answer:**  
- The network created in the **Creation process** reaches up to the **Building Apparatus**, which may sometimes be located inside the building (e.g., PTE – Punto Terminazione Edificio).  
- During **Delivery** (i.e., order activation), the network is extended from the **Building Apparatus** to the customer’s home to provide the optical fiber connection.  
- Therefore, network length is generally considered **from the Building Apparatus to the POP**, while the segment from the building to the customer is handled separately during delivery.

---

## 2. Building Apparatus Location

**Question:**  
Is the Building Apparatus located inside or outside the building?

**Answer:**  
- **Inside the building:** Type **PTE** (Punto Terminazione Edificio).  
- **Outside the building:** Type **PTA** (Punto Terminazione Arretrato). PTA can be:  
  - **Aerial** – e.g., installed on the façade of the building.  
  - **Underground** – e.g., in a manhole.

---

## 3. Circular Paths / Loops in Qlik

**Question:**  
In Qlik, a **circular path (loop)** appears in the network, while the database shows `iscyclic = false`. Could this be a visualization issue or data from different models?

**Answer:**  
- Verify the network at points where it **branches** (bifurcations).  
- Check if **two different network paths** originate from the same point in the **recursive table**.  
- Sometimes loops in Qlik are **only a visualization effect** and do not correspond to actual cycles in the data.

---

## 4. POP to PFP Paths

**Note:**  
- There may be unusual paths from **POP to PFP**.  
- These should be carefully checked in the data model to confirm whether they represent true network routes or visualization artifacts.

---

This README is intended to clarify how network elements are represented, how lengths are calculated, and how to interpret potential loops in visualization tools like Qlik.




#ITALIANO : 
# Rete Open Fiber – Apparato Edificio e Lunghezza della Rete

Questo documento spiega gli aspetti principali relativi all'**Apparato Edificio** nella rete di Open Fiber, come calcolare la lunghezza della rete e alcune note su possibili percorsi circolari nella visualizzazione.

---

## 1. Posizione dell'Apparato Edificio

**Domanda:**  
L’Apparato Edificio nella rete di Open Fiber si trova all’interno dell’edificio oppure all’esterno?

**Risposta:**  
- **All'interno dell'edificio:** Tipo **PTE** (Punto Terminazione Edificio).  
- **All'esterno dell'edificio:** Tipo **PTA** (Punto Terminazione Arretrato), che può essere:  
  - **Aereo** – ad esempio sulla facciata del palazzo.  
  - **Interrato** – ad esempio in un pozzetto.

---

## 2. Calcolo della Lunghezza della Rete

**Domanda:**  
Quando calcoliamo la lunghezza della rete, dobbiamo considerarla dalla casa dell’utente fino al POP, oppure dall’Apparato Edificio fino al POP?

**Risposta:**  
- La rete creata nel processo di **Creation** arriva fino all'**Apparato Edificio**, che a volte è situato all'interno dell'edificio (es.: PTE).  
- Durante la fase di **Delivery** (ovvero l'espletamento di un ordine di attivazione), la rete viene progettata e realizzata dall'**Apparato Edificio** fino dentro la casa del cliente che ha richiesto la fibra ottica.  
- Pertanto, la lunghezza della rete è generalmente considerata **dall'Apparato Edificio fino al POP**, mentre il segmento dall'edificio al cliente è gestito separatamente in fase di delivery.

---

## 3. Percorsi Circolari / Loop in Qlik

**Osservazione:**  
In Qlik sembra esserci un **percorso circolare (loop)** nella rete, mentre nel database il campo `iscyclic = false`.

**Note:**  
- Potrebbe essere **solo un effetto di visualizzazione** sulla mappa.  
- Potrebbe anche dipendere dal fatto che i dati provengono da **modelli diversi**.  
- È consigliato verificare se, sul punto in cui la rete si biforca, ci sono **due percorsi di rete diversi** nella **tabella recursive**.





SELECT id,
       path_id
FROM tmp_l3_recursive.pni_recursive
WHERE id = '4026609553665681626';



SELECT id,
       path_id,
       path_des
FROM tmp_l3_recursive.pni_recursive
WHERE id = '4026609553665681626';

#EXTRACT ID FROM DES_ID 
-- 6622851106802910794 questo quardo
-- 6622851106814994316 questo 5 prima row
-- 4026609553343146678 questo 5 secondo row


SELECT *
FROM l3_qlik.pni_dm_pfp_ad
WHERE cod_pfp_ad in (6622851106802910794,
                     6622851106814994316,
                     4026609553343146678);


des_nome_pfp_ad:

BG_02/01E3

BG_02/01W4

BG_02/01E4

![SERF4](foto9.png)

![SERF4](foto8.png)


