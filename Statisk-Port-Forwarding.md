# Opsætning af Statisk Port Forwarding i FortiGate

## 1. Log ind på FortiGate
Log ind på FortiGate-webgrænsefladen via din browser.

---

## 2. Opret en Virtual IP (VIP)
1. Gå til **Policy & Objects > Virtual IPs**.
2. Klik på **Create New**.
3. Udfyld følgende felter:
   - **Name**: Giv VIP’en et navn (f.eks. `WebServer_Port80`).
   - **Interface**: Vælg den eksterne interface, hvor trafikken kommer ind (f.eks. `wan1`).
   - **External IP Address**:
     - Indtast den offentlige IP, der skal modtage trafikken (eller vælg `"All"` for at bruge enhver offentlig IP).
   - **Mapped IP Address**:
     - Indtast den interne IP-adresse på enheden, som trafikken skal videresendes til (f.eks. en webserver).
   - **Port Forwarding**: Slå denne til.
   - **Protocol**: Vælg protokollen (f.eks. `TCP`).
   - **External Service Port**: Indtast den offentlige port (f.eks. `80` for HTTP).
   - **Mapped Service Port**: Indtast den interne port (f.eks. `80` for HTTP).
4. Klik på **OK** for at gemme.

---

## 3. Opret en Firewall Policy
1. Gå til **Policy & Objects > Firewall Policy**.
2. Klik på **Create New**.
3. Udfyld følgende felter:
   - **Name**: Giv politikken et navn (f.eks. `Allow_HTTP_to_WebServer`).
   - **Incoming Interface**: Vælg den eksterne interface (f.eks. `wan1`).
   - **Outgoing Interface**: Vælg den interne interface (f.eks. `lan`).
   - **Source**: Vælg `All` eller en specifik IP-adresse/gruppe, hvis nødvendigt.
   - **Destination**: Vælg den VIP, du oprettede (f.eks. `WebServer_Port80`).
   - **Schedule**: Sæt det til `Always`.
   - **Service**: Vælg den relevante service (f.eks. `HTTP` eller `TCP/80`).
   - **Action**: Sæt det til `Accept`.
   - **NAT**: Deaktiver NAT, da VIP’en allerede håndterer oversættelsen.
4. Klik på **OK** for at gemme.

---

## 4. Test Konfigurationen
- Brug en ekstern enhed til at teste forbindelsen til den offentlige IP og port.
- Du kan bruge værktøjer som `telnet` eller en webbrowser, afhængigt af tjenesten.
