---
title: "Nasıl yapılır: Windows Forms RichTextBox Denetimi ile Sürükleyip Bırakma İşlemlerini Etkinleştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- drag and drop [Windows Forms], richTextBox control
- text boxes [Windows Forms], drag-and-drop operations
- RichTextBox control [Windows Forms], drag-and-drop operations
ms.assetid: ca167d1c-2014-4cf0-96a0-20598470be3b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 91739643aaa2d7fe3ea302d0d35edabbae0ab14f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-drag-and-drop-operations-with-the-windows-forms-richtextbox-control"></a>Nasıl yapılır: Windows Forms RichTextBox Denetimi ile Sürükleyip Bırakma İşlemlerini Etkinleştirme
Windows Forms ile sürükle ve bırak işlemleri <xref:System.Windows.Forms.RichTextBox> denetim işleyerek yapılır <xref:System.Windows.Forms.RichTextBox.DragEnter> ve <xref:System.Windows.Forms.RichTextBox.DragDrop> olaylar. Bu nedenle, sürükle ve bırak işlemleri ile son derece basit <xref:System.Windows.Forms.RichTextBox> denetim.  
  
### <a name="to-enable-drag-operations-in-a-richtextbox-control"></a>RichTextBox denetiminde sürükleme işlemleri etkinleştirmek için  
  
1.  Ayarlama <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> özelliği <xref:System.Windows.Forms.RichTextBox> denetimini `true`.  
  
2.  Olay işleyicisi kod yazma <xref:System.Windows.Forms.RichTextBox.DragEnter> olay. Kullanım bir `if` deyimi sürüklenen verileri (Bu durumda, metin) kabul edilebilir bir türde olduğundan emin olun. <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> Özelliği herhangi bir değere ayarlanabilir <xref:System.Windows.Forms.DragDropEffects> numaralandırması.  
  
    ```vb  
    Private Sub RichTextBox1_DragEnter(ByVal sender As Object, _   
       ByVal e As System.Windows.Forms.DragEventArgs) _   
       Handles RichTextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
          e.Effect = DragDropEffects.Copy  
       Else  
          e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    ```cpp  
    private:  
       void richTextBox1_DragEnter(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          if (e->Data->GetDataPresent(DataFormats::Text))  
             e->Effect = DragDropEffects::Copy;  
          else  
             e->Effect = DragDropEffects::None;  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] ve [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) formun oluşturucuda olay işleyicisi kaydetmek için aşağıdaki kodu yerleştirin.  
  
    ```csharp  
    this.richTextBox1.DragEnter += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragEnter);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragEnter += gcnew  
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragEnter);  
    ```  
  
3.  İşlemek için kod yazma <xref:System.Windows.Forms.RichTextBox.DragDrop> olay. Kullanım <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> sürüklenen veri alma yöntemi.  
  
     Aşağıdaki kod örneğinde ayarlar <xref:System.Windows.Forms.RichTextBox.Text%2A> özelliği <xref:System.Windows.Forms.RichTextBox> sürüklenen veri eşit denetim. Zaten varsa metinde <xref:System.Windows.Forms.RichTextBox> denetim, sürüklenen metin ekleme noktasına eklenir.  
  
    ```vb  
    Private Sub RichTextBox1_DragDrop(ByVal sender As Object, _   
       ByVal e As System.Windows.Forms.DragEventArgs) _   
       Handles RichTextBox1.DragDrop  
       Dim i As Int16   
       Dim s As String  
  
       ' Get start position to drop the text.  
       i = RichTextBox1.SelectionStart  
       s = RichTextBox1.Text.Substring(i)  
       RichTextBox1.Text = RichTextBox1.Text.Substring(0, i)  
  
       ' Drop the text on to the RichTextBox.  
       RichTextBox1.Text = RichTextBox1.Text + _  
          e.Data.GetData(DataFormats.Text).ToString()  
       RichTextBox1.Text = RichTextBox1.Text + s  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       int i;  
       String s;  
  
       // Get start position to drop the text.  
       i = richTextBox1.SelectionStart;  
       s = richTextBox1.Text.Substring(i);  
       richTextBox1.Text = richTextBox1.Text.Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       richTextBox1.Text = richTextBox1.Text +   
          e.Data.GetData(DataFormats.Text).ToString();  
       richTextBox1.Text = richTextBox1.Text + s;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void richTextBox1_DragDrop(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          int i;  
          String ^s;  
  
       // Get start position to drop the text.  
       i = richTextBox1->SelectionStart;  
       s = richTextBox1->Text->Substring(i);  
       richTextBox1->Text = richTextBox1->Text->Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       String ^str = String::Concat(richTextBox1->Text, e->Data  
       ->GetData(DataFormats->Text)->ToString());   
       richTextBox1->Text = String::Concat(str, s);  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] ve [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) formun oluşturucuda olay işleyicisi kaydetmek için aşağıdaki kodu yerleştirin.  
  
    ```csharp  
    this.richTextBox1.DragDrop += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragDrop);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragDrop += gcnew   
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragDrop);  
    ```  
  
### <a name="to-test-the-drag-and-drop-functionality-in-your-application"></a>Uygulamanızda sürükle ve bırak işlevselliğini sınamak için  
  
1.  Kaydedin ve uygulamanızı oluşturun. Çalışırken, WordPad çalıştırın.  
  
     WordPad sürükle ve bırak işlemleri sağlayan Windows tarafından yüklenen bir metin Düzenleyicisi ' dir. Erişilebilir durumda tıklayarak **Başlat** düğmesi, seçme **çalıştırmak**yazarak `WordPad` metin kutusunda **çalıştırmak** iletişim kutusunu ve ardından  **Tamam**.  
  
2.  WordPad açıldıktan sonra bir metin dizesinin içinde yazın. Fare kullanarak, metni seçin ve ardından seçili metnin üzerine sürükleyin <xref:System.Windows.Forms.RichTextBox> Windows uygulamanız denetiminde.  
  
     Fareyi üzerine geldiğinizde dikkat <xref:System.Windows.Forms.RichTextBox> denetimi (ve sonuç olarak, Yükselt <xref:System.Windows.Forms.RichTextBox.DragEnter> olay), fare işaretçisini değişir ve seçili metne düşürebilir <xref:System.Windows.Forms.RichTextBox> denetim.  
  
     Seçili metni fare düğmesini bıraktığınızda, bırakılan (diğer bir deyişle, <xref:System.Windows.Forms.RichTextBox.DragDrop> olayı) ve içinde eklenen <xref:System.Windows.Forms.RichTextBox> denetim.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.RichTextBox>  
 [Nasıl yapılır: uygulamalar arasında sürükle ve bırak işlemleri gerçekleştirme](../../../../docs/framework/winforms/advanced/how-to-perform-drag-and-drop-operations-between-applications.md)  
 [RichTextBox denetimi](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Windows Forms'ta kullanılacak denetimler](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
