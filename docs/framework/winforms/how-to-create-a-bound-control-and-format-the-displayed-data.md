---
title: 'Vorgehensweise: Erstellen eines gebundenen Steuerelements und Formatieren der angezeigten Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: 543775894994c518d6069f697b145cedaa7af5b0
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015662"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a>Vorgehensweise: Erstellen eines gebundenen Steuerelements und Formatieren der angezeigten Daten

Mit Windows Forms Datenbindung können Sie die Daten, die in einem Daten gebundenen Steuerelement angezeigt werden, mithilfe des Dialog Felds **Formatierung und erweiterte Bindung** formatieren.

## <a name="to-bind-a-control-and-format-the-displayed-data"></a>So binden Sie ein Steuerelement und Formatieren der angezeigten Daten

1. Stellen Sie die Verbindung zu einer Datenquelle her. Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit einer Datenquelle](../data/adonet/connecting-to-a-data-source.md).

2. Wählen Sie in Visual Studio das-Steuerelement auf dem Formular aus, und öffnen Sie dann das **Eigenschaften** Fenster.

3. Erweitern Sie die Eigenschaft **(DataBindings)** , und klicken Sie dann im Feld **(erweitert)** auf die Schaltfläche mit![den Auslassungs Punkten (die Schaltfläche mit den Auslassungs Punkten (.](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)..) im Eigenschaftenfenster von Visual Studio), um **Formatierung und erweitert anzuzeigen.** Dialogfeld "Bindung", das eine komplette Liste der Eigenschaften für dieses Steuerelement enthält.

4. Wählen Sie die Eigenschaft aus, die Sie binden möchten, und wählen Sie dann den **Bindungs** Pfeil aus.

     Nun wird eine Liste verfügbarer Datenquellen angezeigt.

5. Erweitern Sie die Datenquelle, die Sie für die Bindung verwenden möchten, bis Sie das gewünschte einzelne Datenelement finden.

     Wenn die Bindung beispielsweise an einen Spaltenwert in einer Dataset-Tabelle erfolgen soll, erweitern Sie den Namen des Datasets, und erweitern sie dann den Tabellennamen, um die Spaltennamen anzuzeigen.

6. Wählen Sie den Namen eines Elements aus, an das die Bindung erfolgen soll.

7. Wählen Sie im Feld **Formattyp** das Format aus, das Sie auf die im Steuerelement angezeigten Daten anwenden möchten.

     In jedem Fall können Sie den Wert festlegen, der im Steuerelement angezeigt wird, wenn die Datenquelle <xref:System.DBNull> enthält. Andernfalls sind die Optionen je nach ausgewähltem Formattyp leicht abweichend. In der folgenden Tabelle werden die Formattypen und Optionen angezeigt.

    |Formattyp|Formatierungsoption|
    |-----------------|-----------------------|
    |Keine Formatierung|Keine Optionen.|
    |Numeric|Geben Sie die Anzahl von Dezimalstellen mit dem auf-ab-Steuerelement für **Dezimalstellen** an.|
    |Währung|Geben Sie die Anzahl von Dezimalstellen mit dem auf-ab-Steuerelement für **Dezimalstellen** an.|
    |Datum/Zeit|Wählen Sie aus, wie das Datum und die Uhrzeit angezeigt werden sollen, indem Sie eines der Elemente im Feld Typauswahl auswählen.|
    |Wissenschaftlich|Geben Sie die Anzahl von Dezimalstellen mit dem auf-ab-Steuerelement für **Dezimalstellen** an.|
    |Benutzerdefiniert|Geben Sie eine benutzerdefinierte Formatzeichenfolge ein.<br /><br /> Weitere Informationen finden Sie unter [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md). **Hinweis**:  Bei benutzerdefinierten Formatzeichenfolgen kann ein erfolgreicher Roundtrip zwischen Datenquelle und gebundenem Steuerelement nicht garantiert werden Behandeln Sie stattdessen das <xref:System.Windows.Forms.Binding.Parse>- oder <xref:System.Windows.Forms.Binding.Format>-Ereignis für die Bindung, und wenden Sie im Ereignisbehandlungscode eine benutzerdefinierte Formatierung an.|

8. Wählen Sie **OK** aus, um das Dialogfeld **Formatierung und erweiterte Bindung** zu schließen und zum Eigenschaftenfenster zurückzukehren.

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen eines einfach gebundenen Steuer Elements in einem Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Validierung von Benutzereingaben in Windows Forms](user-input-validation-in-windows-forms.md)
- [Windows Forms-Datenbindung](windows-forms-data-binding.md)
