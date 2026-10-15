# Game Server Setup & Domain Guide / Server Opsætning & Domæne Guide

Select your language / Vælg dit sprog:
* [English (#english)](#english)
* [Dansk (#dansk)](#dansk)
* [Deutsch (#deutsch)](#deutsch)
* [Español (#español)](#español)
* [Français (#français)](#français)
* [Svenska (#svenska)](#svenska)

---

## English

### 1. Domain & DNS Setup (Pterodactyl)
To connect your server without typing a port, you must configure your DNS settings.

#### Option A: Using the Community Subdomain (`mtcore.dk`)
If you are using the community subdomain, point your server traffic to the node IP and port provided in your panel.
* **Type:** `A` | **Name:** `yourserver` | **Value:** `Node_IP`
* **Type:** `SRV` (See below for game-specific SRV rules)

#### Option B: Using Your Own Custom Domain
If you bought your own domain (e.g., `mycommunity.com`), log in to your DNS provider (Cloudflare, GoDaddy, Namecheap) and create these records:

#### Minecraft DNS Configuration (No Port Needed)
Create an **SRV** record to map your custom subdomain to the server port:
* **Type:** `SRV`
* **Name:** `play` (or `@` for root domain)
* **Service:** `_minecraft`
* **Protocol:** `_tcp`
* **TTL:** `Automatic` or `3600`
* **Priority:** `0`
* **Weight:** `5`
* **Port:** `Your_Pterodactyl_Server_Port`
* **Target:** `yourserver.mtcore.dk` or your root `A` record pointing to the node.

#### FiveM DNS Configuration (No Port Needed)
Create an **SRV** record for your FiveM server connection:
* **Type:** `SRV`
* **Name:** `cfx` (or `@` for root domain)
* **Service:** `_cfx`
* **Protocol:** `_udp`
* **TTL:** `Automatic` or `3600`
* **Priority:** `0`
* **Weight:** `5`
* **Port:** `Your_Pterodactyl_FiveM_Port`
* **Target:** Your root `A` record pointing to the game node.

---

### 2. Pterodactyl Panel Tutorial
#### File Management & SFTP
1. Navigate to the **File Manager** tab in Pterodactyl.
2. For large uploads, use SFTP. Click on **Settings** to find your SFTP connection details.
3. Download an SFTP client like [FileZilla](https://filezilla-project.org) or [WinSCP](https://winscp.net).
4. Connect using your panel password and drag-and-drop files directly.

#### Database Creation
1. Go to the **Databases** tab.
2. Click **New Database**, give it a name, and click create.
3. Click the eye icon to reveal the DB password and connection strings for your plugins/scripts.

---

### 3. Server Configuration & Development
#### Minecraft Server
* **Plugins & Mods:** Upload your `.jar` files into the `plugins` folder (Spigot/Paper) or `mods` folder (Forge/Fabric).
* **Server Properties:** Edit `server.properties` directly in the panel browser to change game modes, motd, or difficulty.

#### FiveM Server
* **Adding Resources:** Upload scripts into the `resources` folder.
* **Server Configuration:** Add `ensure script_name` to your `server.cfg` file located in the root directory to activate your resources.

---

## Dansk

### 1. Domæne & DNS Opsætning (Pterodactyl)
For at forbinde til din server uden at indtaste port, skal du konfigurere dine DNS-indstillinger.

#### Mulighed A: Brug af fællesskabets subdomæne (`mtcore.dk`)
Hvis du bruger fællesskabets subdomæne, skal du pege din servertrafik til den node-IP og port, der er opgivet i dit panel.
* **Type:** `A` | **Navn:** `dinserver` | **Værdi:** `Node_IP`
* **Type:** `SRV` (Se nedenfor for spilspecifikke SRV-regler)

#### Mulighed B: Brug af dit eget personlige domæne
Hvis du har købt dit eget domæne (f.eks. `mitcommunity.dk`), skal du logge ind på din DNS-udbyder (Cloudflare, GoDaddy) og oprette disse records:

#### Minecraft DNS Konfiguration (Uden Port)
Opret en **SRV** record for at mappe dit subdomæne to serverporten:
* **Type:** `SRV`
* **Navn:** `play` (eller `@` for hoveddomænet)
* **Service:** `_minecraft`
* **Protokol:** `_tcp`
* **TTL:** `Automatisk`
* **Prioritet:** `0`
* **Vægt:** `5`
* **Port:** `Din_Pterodactyl_Server_Port`
* **Mål (Target):** `dinserver.mtcore.dk` eller din hoved `A` record.

#### FiveM DNS Konfiguration (Uden Port)
Opret en **SRV** record for din FiveM serverforbindelse:
* **Type:** `SRV`
* **Navn:** `cfx` (eller `@` for hoveddomænet)
* **Service:** `_cfx`
* **Protokol:** `_udp`
* **TTL:** `Automatisk`
* **Prioritet:** `0`
* **Vægt:** `5`
* **Port:** `Din_Pterodactyl_FiveM_Port`
* **Mål (Target):** Din hoved `A` record, der peger på noden.

---

### 2. Pterodactyl Panel Guide
#### Filhåndtering & SFTP
1. Gå til fanen **File Manager** i Pterodactyl.
2. Til store filer bør du bruge SFTP. Klik på **Settings** for at finde dine SFTP-loginoplysninger.
3. Download en SFTP-klient som [FileZilla](https://filezilla-project.org) eller [WinSCP](https://winscp.net).
4. Forbind ved hjælp af din panel-adgangskode og træk filer over.

#### Oprettelse af Database
1. Gå til fanen **Databases**.
2. Klik på **New Database**, giv den et navn, og tryk opret.
3. Klik på øje-ikonet for at se koderne til dine plugins/scripts.

---

### 3. Serverkonfiguration & Udvikling
#### Minecraft Server
* **Plugins & Mods:** Upload dine `.jar` filer til `plugins` mappen (Spigot/Paper) or `mods` mappen (Forge/Fabric).
* **Server Indstillinger:** Rediger `server.properties` direkte i panelet for at ændre motd eller sværhedsgrad.

#### FiveM Server
* **Tilføjelse af Resources:** Upload scripts/scripts-mapper til mappen `resources`.
* **Server Konfiguration:** Tilføj `ensure script_navn` i din `server.cfg` fil i rodmappen for at aktivere dine scripts.

---

## Deutsch

### 1. Domain- und DNS-Einrichtung (Pterodactyl)
Um eine Verbindung zu Ihrem Server herzustellen, ohne einen Port einzugeben, müssen Sie Ihre DNS-Einstellungen konfigurieren.

#### Option A: Verwendung der Community-Subdomain (`mtcore.dk`)
* **Typ:** `A` | **Name:** `deinserver` | **Wert:** `Node_IP`
* **Typ:** `SRV` (Siehe unten für spielspezifische SRV-Regeln)

#### Option B: Verwendung Ihrer eigenen benutzerdefinierten Domain
Melden Sie sich bei Ihrem DNS-Anbieter (z. B. Cloudflare) an und erstellen Sie folgende Einträge:

#### Minecraft DNS-Konfiguration (Kein Port erforderlich)
* **Typ:** `SRV` | **Name:** `play` | **Dienst:** `_minecraft` | **Protokoll:** `_tcp`
* **Priorität:** `0` | **Gewichtung:** `5` | **Port:** `Dein_Pterodactyl_Port` | **Ziel:** Deine `A`-Adresse.

#### FiveM DNS-Konfiguration (Kein Port erforderlich)
* **Typ:** `SRV` | **Name:** `cfx` | **Dienst:** `_cfx` | **Protokoll:** `_udp`
* **Priorität:** `0` | **Gewichtung:** `5` | **Port:** `Dein_FiveM_Port` | **Ziel:** Deine `A`-Adresse.

---

### 2. Pterodactyl Panel Tutorial
#### Dateiverwaltung & SFTP
1. Nutzen Sie den **File Manager** oder verbinden Sie sich über SFTP unter **Settings**.
2. Verwenden Sie Programme wie [FileZilla](https://filezilla-project.org).

#### Datenbankerstellung
1. Unter **Databases** auf **New Database** klicken, um eine MySQL-Datenbank für Ihre Skripte zu erstellen.

---

### 3. Serverkonfiguration
* **Minecraft:** `.jar`-Dateien in den Ordner `plugins` oder `mods` hochladen.
* **FiveM:** Skripte in den Ordner `resources` hochladen und in der `server.cfg` mittels `ensure skriptname` eintragen.

---

## Español

### 1. Configuración de Dominio y DNS (Pterodactyl)
Para conectarse a su servidor ohne introducir un puerto, debe configurar sus registros DNS.

#### Opción A: Usar el subdominio de la comunidad (`mtcore.dk`)
* **Tipo:** `A` | **Nombre:** `tuservidor` | **Valor:** `Node_IP`
* **Tipo:** `SRV` (Ver reglas específicas abajo)

#### Opción B: Usar su propio dominio personalizado
Inicie sesión en su proveedor DNS (Cloudflare, GoDaddy) y cree los siguientes registros:

#### Configuración DNS para Minecraft (Sin Puerto)
* **Tipo:** `SRV` | **Nombre:** `play` | **Servicio:** `_minecraft` | **Protocolo:** `_tcp`
* **Prioridad:** `0` | **Peso:** `5` | **Puerto:** `Tu_Puerto_Minecraft` | **Destino:** Tu registro `A`.

#### Configuración DNS para FiveM (Sin Puerto)
* **Tipo:** `SRV` | **Nombre:** `cfx` | **Servicio:** `_cfx` | **Protocolo:** `_udp`
* **Prioridad:** `0` | **Peso:** `5` | **Puerto:** `Tu_Puerto_FiveM` | **Destino:** Tu registro `A`.

---

### 2. Tutorial del Panel Pterodactyl
#### Gestión de Archivos y SFTP
1. Vaya a **File Manager** o use SFTP en la pestaña **Settings**.
2. Use clientes como [FileZilla](https://filezilla-project.org) para subir carpetas grandes.

#### Creación de Bases de Datos
1. En la pestaña **Databases**, haga clic en **New Database** para generar credenciales MySQL.

---

### 3. Desarrollo del Servidor
* **Minecraft:** Suba los archivos `.jar` en la carpeta `plugins` o `mods`.
* **FiveM:** Suba los scripts a la carpeta `resources` y actívelos agregando `ensure nombre_del_script` en su `server.cfg`.

---

## Français

### 1. Configuration du Domaine & DNS (Pterodactyl)
Pour vous connecter à votre serveur sans taper de port, vous devez configurer vos paramètres DNS.

#### Option A: Utiliser le sous-domaine communautaire (`mtcore.dk`)
* **Type:** `A` | **Nom:** `tonserveur` | **Valeur:** `Node_IP`
* **Type:** `SRV` (Voir règles ci-dessous)

#### Option B: Utiliser votre propre domaine personnalisé
Connectez-vous à votre bureau d'enregistrement DNS (Cloudflare, etc.) et créez ces enregistrements :

#### Configuration DNS Minecraft (Sans Port)
* **Type:** `SRV` | **Nom:** `play` | **Service:** `_minecraft` | **Protocole:** `_tcp`
* **Priorité:** `0` | **Poids:** `5` | **Port:** `Votre_Port_Minecraft` | **Cible:** Votre enregistrement `A`.

#### Configuration DNS FiveM (Sans Port)
* **Type:** `SRV` | **Nom:** `cfx` | **Service:** `_cfx` | **Protocole:** `_udp`
* **Priorité:** `0` | **Poids:** `5` | **Port:** `Votre_Port_FiveM` | **Cible:** Votre enregistrement `A`.

---

### 2. Tutoriel Panel Pterodactyl
#### Gestion des fichiers & SFTP
1. Accédez à l'onglet **File Manager** ou configurez SFTP via **Settings**.
2. Utilisez un client tel que [FileZilla](https://filezilla-project.org).

#### Création de Base de Données
