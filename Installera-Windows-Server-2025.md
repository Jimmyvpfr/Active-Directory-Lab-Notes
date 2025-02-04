# Installera Windows Server 2025 via Virtual Box

[Windows Server 2025 Download](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2025)  
[Windows 11 Download](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-11-enterprise)  


Först ladda ner iso från microsoft. Evaluation version är gratis i 180 dagar.  
Skapa en Virtual Machine med windows server 2025:

Klicka new 
Fyll I namn, t.ex. Domain controller eller något annat. 
Välj other version x64
Klicka finish
Detta skapar en tom VM utan något operativsystem.

Nu ska vi fördela resurser från vår värddator till vår VM.
Högerklicka på den nya VM och klicka settings
Vissa fält är gråa eftersom jag kör min vm samtidigt som jag tog screenshots.
Under system fördelar vi Ram minne och processor cpu
Jag har ökat mina resurser en aning men jag ser till att inte dra för mycket resurser från min värddator. 
Under rubriken network skapar vi 2 adapters. Den första som NAT**
Den andra Internal network**
Klicka ok.

När vi öppnar vi VM genom att dubbelklicka på den.
Vi blir ombedda att installera operativsystemet och då väljer vi iso filen som vi laddat ner från microsofts hemsida. 
Sedan kan displayen bli svart eller mörkblå, och den kan vara så väldigt länge. Då är det viktigt att inte avbryta processen eftersom windows arbetar i bakgrunden, ha tålamod. 

När vi sedan blir ombedda att klicka oss vidare i windows-installationen så klickar vi oss igenom 

### **Vad gör VirtualBox Guest Additions?**
**VirtualBox Guest Additions** är en uppsättning drivrutiner och programvara som installeras på gästoperativsystemet (VM:n) för att förbättra prestanda och funktionalitet.

---

### **Fördelar med VirtualBox Guest Additions**
✅ **Bättre grafikprestanda**  
   - Aktiverar hårdvaruaccelererad grafik.  
   - Möjliggör **dynamisk skärmstorlek och fullskärmsläge**.  

✅ **Delade mappar**  
   - Låter dig dela filer mellan värddatorn och den virtuella maskinen utan att behöva använda nätverksdelning.

✅ **Musintegration**  
   - Gör att muspekaren **flyter sömlöst** mellan gäst- och värdsystemet utan att behöva trycka på en knapp för att frigöra den.

✅ **Urklippsdelning**  
   - Kopiera och klistra in mellan gäst- och värddatorn.

✅ **Dra och släpp-funktionalitet**  
   - Dra och släpp filer mellan värddatorn och den virtuella maskinen.

✅ **Synkroniserad tid**  
   - Synkroniserar klockan i VM:n med värddatorns systemtid.

✅ **Förbättrad nätverks- och USB-stöd**  
   - Ger bättre nätverkshantering och stöd för USB-enheter.

---

### **Hur installerar man VirtualBox Guest Additions?**
1. **Starta din virtuella maskin** (Windows/Linux).
2. **Öppna menyn "Devices" i VirtualBox**.
3. Klicka på **"Insert Guest Additions CD Image"**.
4. Inne i VM:n:
   - **Windows**: Öppna filen `VBoxWindowsAdditions.exe` och installera.
   - **Linux**: Montera ISO och kör `VBoxLinuxAdditions.run`.
5. **Starta om din VM**.

---

**Vill du hjälp att installera det på din Active Directory-labb? 😊**

Guest Additions

NICs vm network 2 st 

Identifiera nätverksadaptrar och döpa om dem till något som går att urskilja lätt.  
döpa om datorn till något lättare som DC 


Ge interna nätverket en IP adress 

## Installera domän
Add roles and features, installera 

promote to DC  
add new forest och välja namn och lösenord  
klicka ut DNS delegation  
next... install... reboot

## Skapa Admin användare
öppna active Directory users and computers

högerklicka på domän -> new -> Organizational unit  
Ge namnet _ADMINS  
Högerklicka på _ADMINS -> new -> user  
Fyll i namn och user logon: a-jgrafstrom  
Skapa password
högerklicka på user -> properties -> member of -> add  
enter the object names: Domain Admin -> check name -> apply  
Logga ut och logga in på admin user  

## RAS/NAT