---
title: "İzlenecek yol: Çalışma Zamanında Durum Çubuğu Bilgilerini Güncelleştirme"
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
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6c67aa303f375734408201ce15d1c3db3dc32c8e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a><span data-ttu-id="e12d0-102">İzlenecek yol: Çalışma Zamanında Durum Çubuğu Bilgilerini Güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="e12d0-102">Walkthrough: Updating Status Bar Information at Run Time</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="e12d0-103"><xref:System.Windows.Forms.StatusStrip> Ve <xref:System.Windows.Forms.ToolStripStatusLabel> denetimleri değiştirin ve işlevsellik eklemek <xref:System.Windows.Forms.StatusBar> ve <xref:System.Windows.Forms.StatusBarPanel> denetler; ancak, <xref:System.Windows.Forms.StatusBar> ve <xref:System.Windows.Forms.StatusBarPanel> denetimleri korunur geriye dönük uyumluluk ve gelecekte kullanım için ise, ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="e12d0-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="e12d0-104">Genellikle, bir program, çalışma zamanında dinamik olarak güncelleştir uygulama durumu veya başka bir kullanıcı etkileşimi değişikliklere göre durum çubuğu panellerinin içeriğini çağırır.</span><span class="sxs-lookup"><span data-stu-id="e12d0-104">Often, a program will call for you to update the contents of status bar panels dynamically at run time, based on changes to application state or other user interaction.</span></span> <span data-ttu-id="e12d0-105">Bu anahtarları CAPS LOCK, NUM LOCK veya SCROLL LOCK gibi etkinleştirilir kullanıcılar sinyal veya tarih veya saat kullanışlı bir başvuru olarak sağlamak için genel bir yoludur.</span><span class="sxs-lookup"><span data-stu-id="e12d0-105">This is a common way to signal users that keys such as the CAPS LOCK, NUM LOCK, or SCROLL LOCK are enabled, or to provide the date or a clock as a convenient reference.</span></span>  
  
 <span data-ttu-id="e12d0-106">Aşağıdaki örnekte, bir örneğini kullanacağı <xref:System.Windows.Forms.StatusBarPanel> bir saat barındırmak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="e12d0-106">In the following example, you will use an instance of the <xref:System.Windows.Forms.StatusBarPanel> class to host a clock.</span></span>  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a><span data-ttu-id="e12d0-107">Durum çubuğu güncelleştirmek için hazır hale getirmek için</span><span class="sxs-lookup"><span data-stu-id="e12d0-107">To get the status bar ready for updating</span></span>  
  
1.  <span data-ttu-id="e12d0-108">Yeni bir Windows form oluşturun.</span><span class="sxs-lookup"><span data-stu-id="e12d0-108">Create a new Windows form.</span></span>  
  
2.  <span data-ttu-id="e12d0-109">Ekleme bir <xref:System.Windows.Forms.StatusBar> Formunuza denetim.</span><span class="sxs-lookup"><span data-stu-id="e12d0-109">Add a <xref:System.Windows.Forms.StatusBar> control to your form.</span></span> <span data-ttu-id="e12d0-110">Ayrıntılar için bkz [nasıl yapılır: Windows Forms denetimlerine ekleme](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e12d0-110">For details, see [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
3.  <span data-ttu-id="e12d0-111">Durum çubuğu paneline ekleyebilir, <xref:System.Windows.Forms.StatusBar> denetim.</span><span class="sxs-lookup"><span data-stu-id="e12d0-111">Add a status bar panel to your <xref:System.Windows.Forms.StatusBar> control.</span></span> <span data-ttu-id="e12d0-112">Ayrıntılar için bkz [nasıl yapılır: bir StatusBar denetimine paneller ekleme](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).</span><span class="sxs-lookup"><span data-stu-id="e12d0-112">For details, see [How to: Add Panels to a StatusBar Control](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).</span></span>  
  
4.  <span data-ttu-id="e12d0-113">İçin <xref:System.Windows.Forms.StatusBar> formunuza, eklediğiniz denetimini ayarlama <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> özelliğine `true`.</span><span class="sxs-lookup"><span data-stu-id="e12d0-113">For the <xref:System.Windows.Forms.StatusBar> control you added to your form, set the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true`.</span></span>  
  
5.  <span data-ttu-id="e12d0-114">Windows Forms eklemek <xref:System.Windows.Forms.Timer> forma bileşen.</span><span class="sxs-lookup"><span data-stu-id="e12d0-114">Add a Windows Forms <xref:System.Windows.Forms.Timer> component to the form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e12d0-115">Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> bileşeni, bir Windows Forms ortamı için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="e12d0-115">The Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="e12d0-116">Bir sunucu ortamı için uygun bir süreölçer gerekirse bkz [sunucu tabanlı zamanlayıcılar giriş](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="e12d0-116">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
6.  <span data-ttu-id="e12d0-117">Ayarlama <xref:System.Windows.Forms.Timer.Enabled%2A> özelliğine `true`.</span><span class="sxs-lookup"><span data-stu-id="e12d0-117">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>  
  
7.  <span data-ttu-id="e12d0-118">Ayarlama <xref:System.Windows.Forms.Timer.Interval%2A> özelliği <xref:System.Windows.Forms.Timer> 30000 için.</span><span class="sxs-lookup"><span data-stu-id="e12d0-118">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> to 30000.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e12d0-119"><xref:System.Windows.Forms.Timer.Interval%2A> Özelliği <xref:System.Windows.Forms.Timer> bileşen doğru zaman görüntülenen zaman yansıtılmasını sağlamak için 30 saniye (30.000 milisaniye) olarak ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="e12d0-119">The <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> component is set to 30 seconds (30,000 milliseconds) to ensure that an accurate time is reflected in the time displayed.</span></span>  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a><span data-ttu-id="e12d0-120">Durum çubuğu güncelleştirmek için Zamanlayıcı uygulamak için</span><span class="sxs-lookup"><span data-stu-id="e12d0-120">To implement the timer to update the status bar</span></span>  
  
1.  <span data-ttu-id="e12d0-121">Olay işleyicisinin aşağıdaki kodu ekleyin <xref:System.Windows.Forms.Timer> panelini güncelleştirmek için bileşen <xref:System.Windows.Forms.StatusBar> denetim.</span><span class="sxs-lookup"><span data-stu-id="e12d0-121">Insert the following code into the event handler of the <xref:System.Windows.Forms.Timer> component to update the panel of the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     <span data-ttu-id="e12d0-122">Bu noktada, uygulamayı çalıştırın ve durum çubuğu Masası'nda çalışan saati gözlemlemek hazırsınız.</span><span class="sxs-lookup"><span data-stu-id="e12d0-122">At this point, you are ready to run the application and observe the clock running in the status bar panel.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="e12d0-123">Uygulamayı test etmek için</span><span class="sxs-lookup"><span data-stu-id="e12d0-123">To test the application</span></span>  
  
1.  <span data-ttu-id="e12d0-124">Uygulamada hata ayıklama ve çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e12d0-124">Debug the application and press F5 to run it.</span></span> <span data-ttu-id="e12d0-125">Hata ayıklama hakkında daha fazla bilgi için bkz [Visual Studio'da hata ayıklamayı](/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="e12d0-125">For details about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e12d0-126">Yaklaşık olarak 30 durum çubuğunda görünmesini saniye saat sürer.</span><span class="sxs-lookup"><span data-stu-id="e12d0-126">It will take approximately 30 seconds for the clock to appear in the status bar.</span></span> <span data-ttu-id="e12d0-127">Bu olası en doğru zamanı elde etmektir.</span><span class="sxs-lookup"><span data-stu-id="e12d0-127">This is to get the most accurate time possible.</span></span> <span data-ttu-id="e12d0-128">Buna karşılık, er görünür saati yapmak için değeri azaltabilir <xref:System.Windows.Forms.Timer.Interval%2A> ayarlanan önceki yordamdaki adım 7'deki özelliği.</span><span class="sxs-lookup"><span data-stu-id="e12d0-128">Conversely, to make the clock appear sooner, you can reduce the value of the <xref:System.Windows.Forms.Timer.Interval%2A> property you set in step 7 in the previous procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e12d0-129">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e12d0-129">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="e12d0-130">Nasıl yapılır: bir StatusBar denetimine panel ekleme</span><span class="sxs-lookup"><span data-stu-id="e12d0-130">How to: Add Panels to a StatusBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)  
 [<span data-ttu-id="e12d0-131">Nasıl yapılır: Windows Forms StatusBar denetiminde hangi panele tıklandığını belirleme</span><span class="sxs-lookup"><span data-stu-id="e12d0-131">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [<span data-ttu-id="e12d0-132">StatusBar denetimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="e12d0-132">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)