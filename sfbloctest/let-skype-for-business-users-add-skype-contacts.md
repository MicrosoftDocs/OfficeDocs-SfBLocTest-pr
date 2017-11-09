---
title: Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 10/11/2017
ms.audience: Admin
ms.topic: How To
ms.service: OFFICE365
description: See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. 
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.technology:
- Office 365 Enterprise
- Office 365 Enterprise admin
- Office 365 Midsize Business admin
- Office 365 Small Business admin
- Skype for Business
- Skype for Business admin center
- Skype for Business Online
- Skype for Business Online admin center
ms.set-free-tag:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
---



# Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den  [Haftungsausschluss](08666236-1894-42ae-8846-e49232bbc460.md#MT_Footer). Die englische Version des Artikels ist als Referenz hier verfügbar:  [hier](https://support.office.com/en-us/article/08666236-1894-42ae-8846-e49232bbc460). 
  
    
    


Mit Skype for Business können Ihre Benutzer nach beliebigen Benutzern von Skype - der kostenlosen App - suchen und Chatnachrichten mit ihnen austauschen. In diesem Artikel wird erläutert, was Sie tun müssen, damit die Benutzer Skype-Kontakte hinzufügen können. 
  
    
    


Sie benötigen  [Informationen zu Administratorrollen von Office 365](about-office-365-admin-roles.md) in Office 365 zu diesem Zweck.
  
    
    


1. Melden Sie sich mit Ihrem Office 365-Administratorkonto bei  [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) an.
    
  
2. Gehen Sie in Office 365 Admin Center zu **Admin Center** > **Skype for Business**. 
    
    ![Choose the Skype for Business admin center.](images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
    
    

    
  
3. Wählen Sie unter **Skype for Business Admin Center**die Option **Organisation** > **Externe Kommunikation**. 
    
  
4. Standardmäßig können Ihre Benutzer mit allen anderen Personen weltweit kommunizieren, die Skype for Business verwenden (vorausgesetzt, Ihre Firewall ist so konfiguriert, dass sie dies zulässt). 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    
    

    
    Wenn Sie möchten, dass Ihre Benutzer mit Skype-Benutzern chatten, ABER nicht mit anderen, die Skype for Business verwenden, wählen Sie **Nur für zulässige Domänen aktivieren** aus. Wenn Sie den Kontakt mit Skype-Benutzern ermöglichen, wird „skype.com" automatisch im Hintergrund als zulässige Domäne hinzugefügt.
    
    Wenn Sie den Kontakt über Skype for Business von allen anderen Unternehmen weltweit mit Ausnahme bestimmter Unternehmen zulassen möchten, wählen Sie **Aktivieren mit Ausnahme der blockierten Domänen** aus. Wählen Sie dann **+** aus, um die entsprechenden Domänen hinzuzufügen. Alle Personen mit Ausnahme derer in diesen Domänen können Kontakt zu Ihnen aufnehmen. (Ein Unternehmen kann diese Option z. B. wählen, wenn ein Rechtsstreit vorliegt und sichergestellt werden muss, dass kein Kontakt zu dem anderen Unternehmen unterhalten wird.)
    
  
5. Wählen Sie **Zulassen, dass Skype for Business zur Kommunikation mit Skype-Benutzern außerhalb Ihres Unternehmens verwendet wird**. 
    
  
6. Wenn Sie die Windows-Firewall verwenden, öffnet Skype for Business die erforderlichen Ports automatisch. 
    
    Wenn Ihre Organisation eine andere Lösung zum Einschränken von Computern in Ihrem Netzwerk verwendet, stellen Sie sicher, dass die Clientcomputer auf alle  [URLs und IP-Adressbereiche von Office 365](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx) für die Skype-Verbindung und die Suche im Skype-Verzeichnis zugreifen können. Dafür kann es erforderlich sein, sie der Liste für zugelassene ausgehende Verbindungen in Ihrer Firewall oder Proxy-Infrastrukturkonfiguration hinzuzufügen.
    
  
7. **WARTEN SIE MIT DEM TEST BIS ZU 24 STUNDEN**. Bei jeder Änderung der Einstellungen für externe Kommunikation kann es bis zu 24 Stunden dauern, bis die Änderungen in allen Rechenzentren übernommen wurden.
    
  
8. Zeigen Sie Ihren Benutzern, wie sie Skype-Kontakte finden und zu ihrer Liste mit Skype for Business-Kontakten hinzufügen können. Verweisen Sie die Benutzer auf  [Suchen nach Personen in Skype for Business](http://technet.microsoft.com/library/b12500ef-e37f-4d22-aade-c11277e53f19%28Office.14%29.aspx).
    
  

## Tests und Problembehandlung

Um Ihr Setup zu testen, benötigen Sie einen Kontakt in Skype, der sich nicht hinter der Firewall Ihrer Firma befindet. Der Kontakt kann mit einem Gmail-Konto, Outlook.com-Konto oder einem anderen E-Mail-Kontotyp angemeldet sein.
  
    
    

1. Warten Sie nach einer Änderung der Einstellungen für externe Kommunikation **BIS ZU 24 STUNDEN, BEVOR SIE TESTS DURCHFÜHREN**.
    
  
2. Melden Sie sich bei Skype for Business ab und dann wieder an, damit Sie die Option zum Durchsuchen des Skype-Verzeichnisses sehen. 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
    
    

    
  
3. Suchen Sie in Skype for Business nach Ihrem Kontakt in Skype, und senden Sie eine Chatanfrage. 
    
    Wenn Sie durch eine Meldung informiert werden, dass die Anfrage aufgrund einer Unternehmensrichtlinie nicht gesendet werden konnte, müssen Sie Ihre  [URLs und IP-Adressbereiche von Office 365](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx) nochmals überprüfen.
    
  
4. Eine weitere Möglichkeit, zu testen, ob die Firewall das Problem darstellt: Gehen Sie zu einem Ort mit WLAN, der sich nicht hinter Ihrer Firewall befindet (zum Beispiel in ein Café), und senden Sie mit Skype for Business eine Chatanfrage an Ihren Skype-Kontakt. 
    
  - **Wenn Sie Ihrem Skype-Kontakt eine Anfrage gesendet haben, die dieser nicht erhalten hat**, bitten Sie ihn, Ihnen eine Chatanfrage zu senden. Wenn das Problem darin bestand, eine Verbindung zwischen Skype und Skype for Business herzustellen, ist das Problem damit oft gelöst.
    
  
  - Wenn die Nachricht im Café gesendet wird, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt. 
    
  

  
    
    

## Was möglich und was nicht möglich ist


- **Skype for Businessfür Mac** ist es nicht möglich, nach Skype-Kontakten zu suchen und mit ihnen zu kommunizieren.
    
  
- Sie können nach Skype-Benutzern suchen, diese können aber nicht nach Skype for Business-Benutzern suchen. Sie müssen diesen Benutzern eine Kontaktanfrage senden, und die Benutzer müssen sich bei Skype anmelden und die Anfrage akzeptieren. Erst dann können Sie Chats mit ihnen führen. 
    
  
- Chat-Nachrichtenverbindungen mit anderen Chat-Dienstanbietern wie Google oder Facebook sind nicht möglich. Sie können Skype for Business nicht zum Senden von Mobiltelefon-Textnachrichten verwenden.
    
  

## Welche Funktionen sind beim Hinzufügen von Skype-Kontakten verfügbar?

Skype-Kontakten, die sich mit ihrem Microsoft-Konto (ehemals Windows Live ID) angemeldet haben, stehen beim Gespräch mit Skype for Business-Benutzern einige, aber nicht alle Funktionen zur Verfügung.
  
    
    


|**Für Skype-Kontakte verfügbar**|**Für Skype-Kontakte nicht verfügbar**|
|:-----|:-----|
| Videounterhaltungen <br/>  Chatnachrichten zwischen zwei Personen <br/>  Anwesenheitsstatus <br/> | Chatunterhaltungen mit mehreren Personen <br/>  Audio- und Videounterhaltungen mit drei oder mehr Personen <br/>  Desktop- und Programmfreigabe <br/> |
   

## 

 *Aktualisierung: Donnerstag, 23. März 2017* 
  
    
    

||
|:-----|
|![Symbol für LinkedIn Learning](images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Neu bei Office 365?**         Entdecken Sie kostenlose Videokurse für **Office 365-Administratoren und IT-Experten**, bereitgestellt von LinkedIn Learning. |
   

## 
<a name="MT_Footer"> </a>


> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  
    
    


## See also
<a name="MT_Footer"> </a>


#### 


  
    
    
 [Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md)
  
    
    
 [Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)
