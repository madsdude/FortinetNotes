
<body>

  <h1>FortiGate Kommandoer</h1>

  <h2>Generelle Kommandoer</h2>
    <pre><code>get system status</code></pre>
    <p>Viser generel information om systemet som firmware version, serial number, uptime osv.</p>

  <pre><code>show system interface &lt;interface-navn&gt;</code></pre>
  <p>Udskift <code>&lt;interface-navn&gt;</code> med det specifikke interface, f.eks. <code>port1</code>.</p>

  <pre><code>execute ping &lt;IP-adresse&gt;</code></pre>
  <p>Bruges til at teste netværksforbindelsen til en IP-adresse.</p>

  <pre><code>execute reboot</code></pre>    
  <p>Genstarter FortiGate.</p>

  <h2>Fejlfinding</h2>
    <pre><code>diagnose sys session list</code></pre>
    <p>Viser en liste over aktive sessions gennem FortiGate.</p>

   <pre><code>diagnose sys top</code></pre>
  <p>Viser CPU- og hukommelsesbrug. Brug <code>shift+m</code> for at sortere efter hukommelsesbrug.</p>

   <pre><code>execute traceroute &lt;IP-adresse&gt;</code></pre>
  <p>Kører en traceroute fra FortiGate.</p>

   <pre><code>execute log filter view-lines &lt;antal-linjer&gt;</code></pre>
   <pre><code>execute log display</code></pre>
   <p>Filtrerer og viser logfiler.</p>

  <pre><code>get router info routing-table all</code></pre>
   <p>Viser routing table.</p>

   <h2>Sikkerhed og Konfiguration</h2>
    <pre><code>show firewall policy</code></pre>
    <p>Viser firewall policies.</p>

   <pre><code>execute backup config ftp &lt;IP-adresse&gt; &lt;brugernavn&gt; &lt;password&gt; &lt;filnavn&gt;</code></pre>
  <p>Sikkerhedskopierer konfigurationsfilen til en FTP-server.</p>

   <pre><code>execute restore config ftp &lt;IP-adresse&gt; &lt;brugernavn&gt; &lt;password&gt; &lt;filnavn&gt;</code></pre>
   <p>Uploader konfiguration til FortiGate.</p>

   <pre><code>config system interface</code></pre>
   <pre><code>edit &lt;interface-navn&gt;</code></pre>
  <pre><code>set allowaccess ssh</code></pre>
   <pre><code>end</code></pre>
   <p>Aktiverer SSH på et interface.</p>

   <pre><code>config system admin</code></pre>
   <pre><code>edit &lt;admin&gt;</code></pre>
   <pre><code>set password &lt;nyt-password&gt;</code></pre>
   <pre><code>end</code></pre>
   <p>Sætter administrator password.</p>

   <h2>Diagnostik og Analyse</h2>
    <pre><code>diagnose ip arp list</code></pre>
    <p>Viser ARP-tabel.</p>

  <pre><code>diagnose sys session list | grep &lt;IP-adresse&gt;</code></pre>
   <p>Filtrerer sessioner baseret på en specifik IP-adresse.</p>

   <pre><code>diagnose sniffer packet any 'host &lt;IP-adresse&gt;' 4</code></pre>
   <p>Overvåger trafik til/fra en bestemt IP-adresse.</p>

  <h2>Opdateringer</h2>
    <pre><code>execute update-now</code></pre>
    <p>Tjekker for nye opdateringer.</p>

  <pre><code>execute restore image ftp &lt;IP-adresse&gt; &lt;brugernavn&gt; &lt;password&gt; &lt;filnavn&gt;</code></pre>
  <p>Installerer en firmware opdatering.</p>

</body>
</html>
