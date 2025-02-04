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
