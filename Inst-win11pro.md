skapa ny vm och mounta iso.

nätverk välj internal network

disable EFI

innan installation av windows tryck **shift + F10** för att öppna command prompt 

skriv **regedit** som är register editor window  

**hkey local machine, system, setup, skapa key = LabConfig**  

i labconfig:  
högerklicka i mappen, new Dword 32 bit med namn: BypassTPMCheck  
högerklicka på filen och klicka modify och skriv 1 istället 0

skapa en likadan fil men namn: BypassSecureBootCheck och gör samma sak.

stäng ner regedit och cmd

genomför installationen. 

när registreringen av windowskonto ska genomföras öppna cmd Shift + F10 och skriv: **oobe\bypassnro**  
**ipconfig /release**
detta gör att installationen kan göras utan internet. 

---

## ansluta till domän

gå in på system> about> domän och workgroup> change

member of ditt domän> ok 

skriv in admin uppgifter a-jgrafström och lösen

---

logga in på en användare till domänet genom att trycka på other user och skriv in tex sbeater Password1

i cmd whoami för att se att användaren är ansluten till domänet.