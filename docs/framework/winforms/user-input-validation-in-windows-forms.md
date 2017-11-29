---
title: "Windows Forms'ta Kullanıcı Girdisi Doğrulama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48a28db24731f9aa248bb149c9f19a57cf76bbf1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="user-input-validation-in-windows-forms"></a><span data-ttu-id="3468a-102">Windows Forms'ta Kullanıcı Girdisi Doğrulama</span><span class="sxs-lookup"><span data-stu-id="3468a-102">User Input Validation in Windows Forms</span></span>
<span data-ttu-id="3468a-103">Kullanıcılar uygulamanıza veri girdiğinizde, uygulamanızın kullandığı önce verilerin geçerli olduğunu doğrulamak isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3468a-103">When users enter data into your application, you may want to verify that the data is valid before your application uses it.</span></span> <span data-ttu-id="3468a-104">Belirli metin alanları olmaması, sıfır uzunluk, alan bir telefon numarası veya diğer iyi biçimlendirilmiş bir veri türü olarak biçimlendirilmiş olması ya da bir dizeyi bir veritabanı güvenliğinizi aşmaya kullanılabilecek herhangi güvenli olmayan karakterleri içeremez gerektirebilir.</span><span class="sxs-lookup"><span data-stu-id="3468a-104">You may require that certain text fields not be zero-length, that a field be formatted as a telephone number or other type of well-formed data, or that a string not contain any unsafe characters that could be used to compromise the security of a database.</span></span> <span data-ttu-id="3468a-105">Windows Forms, uygulamanızdaki giriş doğrulamak çeşitli yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="3468a-105">Windows Forms provides several ways for you to validate input in your application.</span></span>  
  
## <a name="validation-with-the-maskedtextbox-control"></a><span data-ttu-id="3468a-106">MaskedTextBox denetimi ile doğrulama</span><span class="sxs-lookup"><span data-stu-id="3468a-106">Validation with the MaskedTextBox Control</span></span>  
 <span data-ttu-id="3468a-107">Kullanıcıların, bir telefon numarası ya da bir parça numarası gibi iyi tanımlanmış biçiminde veri girmesini gerektiren gerekiyorsa bunu hızlı ve daha az kod kullanarak gerçekleştirebilirsiniz <xref:System.Windows.Forms.MaskedTextBox> denetim.</span><span class="sxs-lookup"><span data-stu-id="3468a-107">If you need to require users to enter data in a well-defined format, such as a telephone number or a part number, you can accomplish this quickly and with minimal code by using the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span> <span data-ttu-id="3468a-108">A *maskesi* hangi karakterlerin herhangi belirtilen konumda metin kutusuna girilen belirten bir maskeleme dil karakterlerden oluşan bir dize.</span><span class="sxs-lookup"><span data-stu-id="3468a-108">A *mask* is a string made up of characters from a masking language that specifies which characters can be entered at any given position in the text box.</span></span> <span data-ttu-id="3468a-109">Denetim ister bir dizi kullanıcıya görüntüler.</span><span class="sxs-lookup"><span data-stu-id="3468a-109">The control displays a set of prompts to the user.</span></span> <span data-ttu-id="3468a-110">Kullanıcı yanlış bir girdi yazarsa, örneğin, bir basamak gerekli olduğunda, bir harf kullanıcı türleri, denetimi otomatik olarak giriş reddeder.</span><span class="sxs-lookup"><span data-stu-id="3468a-110">If the user types an incorrect entry, for example, the user types a letter when a digit is required, the control will automatically reject the input.</span></span>  
  
 <span data-ttu-id="3468a-111">Tarafından kullanılan maskeleme dil <xref:System.Windows.Forms.MaskedTextBox> çok esnektir.</span><span class="sxs-lookup"><span data-stu-id="3468a-111">The masking language that is used by <xref:System.Windows.Forms.MaskedTextBox> is very flexible.</span></span> <span data-ttu-id="3468a-112">Gerekli karakterler, isteğe bağlı karakter, kısa çizgi ve parantez gibi değişmez değer karakterler, para birimi karakter ve tarih ayırıcıları belirtmenize olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="3468a-112">It allows you to specify required characters, optional characters, literal characters, such as hyphens and parentheses, currency characters, and date separators.</span></span> <span data-ttu-id="3468a-113">İyi ne zaman bir veri kaynağına bağlı denetimi de çalışır.</span><span class="sxs-lookup"><span data-stu-id="3468a-113">The control also works well when bound to a data source.</span></span> <span data-ttu-id="3468a-114"><xref:System.Windows.Forms.Binding.Format> Veri bağlama olayda maskesiyle uyumlu olacak şekilde gelen verileri yeniden biçimlendirmek için kullanılabilir ve <xref:System.Windows.Forms.Binding.Parse> olay veri alanı belirtimlere uymak için giden verileri yeniden biçimlendirmek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3468a-114">The <xref:System.Windows.Forms.Binding.Format> event on a data binding can be used to reformat incoming data to comply with the mask, and the <xref:System.Windows.Forms.Binding.Parse> event can be used to reformat outgoing data to comply with the specifications of the data field.</span></span>  
  
 <span data-ttu-id="3468a-115">Daha fazla bilgi için bkz: [MaskedTextBox denetimi](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3468a-115">For more information, see [MaskedTextBox Control](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md).</span></span>  
  
## <a name="event-driven-validation"></a><span data-ttu-id="3468a-116">Olay kaynaklı doğrulama</span><span class="sxs-lookup"><span data-stu-id="3468a-116">Event-Driven Validation</span></span>  
 <span data-ttu-id="3468a-117">Doğrulama üzerinde tam programsal denetim istediğiniz veya karmaşık doğrulama denetimlerini gerçekleştiren gerekirse, çoğu Windows Forms denetimlerinin yerleşik doğrulama olayları kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="3468a-117">If you want full programmatic control over validation, or need to perform complex validation checks, you should use the validation events built into most Windows Forms controls.</span></span> <span data-ttu-id="3468a-118">Serbest biçimli kullanıcı girişini kabul etme her bir denetimi olan bir <xref:System.Windows.Forms.Control.Validating> denetimi veri doğrulama gerekli olduğunda meydana gelir olay.</span><span class="sxs-lookup"><span data-stu-id="3468a-118">Each control that accepts free-form user input has a <xref:System.Windows.Forms.Control.Validating> event that will occur whenever the control requires data validation.</span></span> <span data-ttu-id="3468a-119">İçinde <xref:System.Windows.Forms.Control.Validating> olay işleme yöntemi, kullanıcı çeşitli yollarla girişi doğrulama.</span><span class="sxs-lookup"><span data-stu-id="3468a-119">In the <xref:System.Windows.Forms.Control.Validating> event-handling method, you can validate user input in several ways.</span></span> <span data-ttu-id="3468a-120">Örneğin, bir posta kodu içermesi gereken bir metin kutusu varsa, aşağıdaki yollarla doğrulama gerçekleştirebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="3468a-120">For example, if you have a text box that must contain a postal code, you can perform the validation in the following ways:</span></span>  
  
-   <span data-ttu-id="3468a-121">Posta kodu posta kodlarının belirli bir gruba ait olması gerekir, kullanıcı tarafından girilen verileri doğrulamak için giriş üzerinde bir dize karşılaştırma gerçekleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3468a-121">If the postal code must belong to a specific group of zip codes, you can perform a string comparison on the input to validate the data entered by the user.</span></span> <span data-ttu-id="3468a-122">Posta kodu {10001, 10002, 10003} kümesinde olmalıdır, örneğin, daha sonra bir dize karşılaştırma verileri doğrulamak için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3468a-122">For example, if the postal code must be in the set {10001, 10002, 10003}, then you can use a string comparison to validate the data.</span></span>  
  
-   <span data-ttu-id="3468a-123">Posta kodu belirli bir formda olması gerekiyorsa kullanıcı tarafından girilen verileri doğrulamak için normal ifadeleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3468a-123">If the postal code must be in a specific form you can use regular expressions to validate the data entered by the user.</span></span> <span data-ttu-id="3468a-124">Örneğin, form doğrulamak için `#####` veya `#####-####`, normal ifade kullanabilirsiniz `^(\d{5})(-\d{4})?$`.</span><span class="sxs-lookup"><span data-stu-id="3468a-124">For example, to validate the form `#####` or `#####-####`, you can use the regular expression `^(\d{5})(-\d{4})?$`.</span></span> <span data-ttu-id="3468a-125">Formun doğrulamak için `A#A #A#`, normal ifade kullanabilirsiniz `[A-Z]\d[A-Z] \d[A-Z]\d`.</span><span class="sxs-lookup"><span data-stu-id="3468a-125">To validate the form `A#A #A#`, you can use the regular expression `[A-Z]\d[A-Z] \d[A-Z]\d`.</span></span> <span data-ttu-id="3468a-126">Normal ifadeler hakkında daha fazla bilgi için bkz: [.NET Framework normal ifadeleri](../../../docs/standard/base-types/regular-expressions.md) ve [normal ifade örnekleri](../../../docs/standard/base-types/regular-expression-examples.md).</span><span class="sxs-lookup"><span data-stu-id="3468a-126">For more information about regular expressions, see [.NET Framework Regular Expressions](../../../docs/standard/base-types/regular-expressions.md) and [Regular Expression Examples](../../../docs/standard/base-types/regular-expression-examples.md).</span></span>  
  
-   <span data-ttu-id="3468a-127">Posta kodu geçerli bir Amerika Birleşik Devletleri posta kodu olmalıdır, kullanıcı tarafından girilen verileri doğrulamak için bir posta kodu Web hizmeti çağrısı.</span><span class="sxs-lookup"><span data-stu-id="3468a-127">If the postal code must be a valid United States Zip code, you could call a Zip code Web service to validate the data entered by the user.</span></span>  
  
 <span data-ttu-id="3468a-128"><xref:System.Windows.Forms.Control.Validating> Olay sağlanmaktadır türünde bir nesne <xref:System.ComponentModel.CancelEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="3468a-128">The <xref:System.Windows.Forms.Control.Validating> event is supplied an object of type <xref:System.ComponentModel.CancelEventArgs>.</span></span> <span data-ttu-id="3468a-129">Denetimin veri geçersiz karar verirseniz, iptal edebilirsiniz <xref:System.Windows.Forms.Control.Validating> bu nesnenin ayarlayarak olay <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> özelliğine `true`.</span><span class="sxs-lookup"><span data-stu-id="3468a-129">If you determine that the control's data is not valid, you can cancel the <xref:System.Windows.Forms.Control.Validating> event by setting this object's <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property to `true`.</span></span> <span data-ttu-id="3468a-130">Ayarlanmamış ise <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> özelliği, Windows Forms, doğrulama için bu denetim başarılı varsayar ve yükseltmek <xref:System.Windows.Forms.Control.Validated> olay.</span><span class="sxs-lookup"><span data-stu-id="3468a-130">If you do not set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property, Windows Forms will assume that validation succeeded for that control, and raise the <xref:System.Windows.Forms.Control.Validated> event.</span></span>  
  
 <span data-ttu-id="3468a-131">Bir e-posta adresini doğrular bir kod örneği için bir <xref:System.Windows.Controls.TextBox>, bkz: <xref:System.Windows.Forms.Control.Validating>.</span><span class="sxs-lookup"><span data-stu-id="3468a-131">For a code example that validates an e-mail address in a <xref:System.Windows.Controls.TextBox>, see <xref:System.Windows.Forms.Control.Validating>.</span></span>  
  
### <a name="data-binding-and-event-driven-validation"></a><span data-ttu-id="3468a-132">Veri bağlama ve olay denetimli doğrulama</span><span class="sxs-lookup"><span data-stu-id="3468a-132">Data Binding and Event-Driven Validation</span></span>  
 <span data-ttu-id="3468a-133">Bir veritabanı tablosu gibi bir veri kaynağına denetimlerinizi bağladıktan doğrulama oldukça yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="3468a-133">Validation is very useful when you have bound your controls to a data source, such as a database table.</span></span> <span data-ttu-id="3468a-134">Doğrulama, kullanarak emin olun, veri kaynağı tarafından gerekli olan biçime denetiminizin veri karşılayan ve onu değil tırnak işaretleri gibi özel karakterler içeren ve geri olduğunu, Yatık çizgi güvensiz olabilir.</span><span class="sxs-lookup"><span data-stu-id="3468a-134">By using validation, you can make sure that your control's data satisfies the format required by the data source, and that it does not contain any special characters such as quotation marks and back slashes that might be unsafe.</span></span>  
  
 <span data-ttu-id="3468a-135">Veri bağlama kullandığınızda, Denetim verilerinde yürütülmesi sırasında veri kaynağıyla eşitlenir <xref:System.Windows.Forms.Control.Validating> olay.</span><span class="sxs-lookup"><span data-stu-id="3468a-135">When you use data binding, the data in your control is synchronized with the data source during execution of the <xref:System.Windows.Forms.Control.Validating> event.</span></span> <span data-ttu-id="3468a-136">İptal ederseniz <xref:System.Windows.Forms.Control.Validating> olay verileri veri kaynağı ile senkronize edilmeyecek.</span><span class="sxs-lookup"><span data-stu-id="3468a-136">If you cancel the <xref:System.Windows.Forms.Control.Validating> event, the data will not be synchronized with the data source.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3468a-137">Gerçekleştikten sonra özel doğrulama varsa <xref:System.Windows.Forms.Control.Validating> olay, onu etkilemez veri bağlama.</span><span class="sxs-lookup"><span data-stu-id="3468a-137">If you have custom validation that takes place after the <xref:System.Windows.Forms.Control.Validating> event, it will not affect the data binding.</span></span> <span data-ttu-id="3468a-138">Örneğin, kod varsa bir <xref:System.Windows.Forms.Control.Validated> veri bağlama iptal etmeyi dener olay, veri bağlama hala oluşur.</span><span class="sxs-lookup"><span data-stu-id="3468a-138">For example, if you have code in a <xref:System.Windows.Forms.Control.Validated> event that attempts to cancel the data binding, the data binding will still occur.</span></span> <span data-ttu-id="3468a-139">Doğrulama gerçekleştirmek için bu durumda <xref:System.Windows.Forms.Control.Validated> olay, denetimin değiştirme **veri kaynağı güncelleme modu** özelliği (**(veri bağlamaları) altında**\\**(Gelişmiş)** ) gelen **OnValidation'ı** için **hiçbir zaman**ve ekleme *denetim*`.DataBindings["`*\<YOURFIELD >*  `"].WriteValue()` doğrulama kodunuzu için.</span><span class="sxs-lookup"><span data-stu-id="3468a-139">In this case, to perform validation in the <xref:System.Windows.Forms.Control.Validated> event, change the control's **Data Source Update Mode** property (**under (Databindings)**\\**(Advanced)**) from **OnValidation** to **Never**, and add *Control*`.DataBindings["`*\<YOURFIELD>*`"].WriteValue()` to your validation code.</span></span>  
  
### <a name="implicit-and-explicit-validation"></a><span data-ttu-id="3468a-140">Örtük ve açık doğrulama</span><span class="sxs-lookup"><span data-stu-id="3468a-140">Implicit and Explicit Validation</span></span>  
 <span data-ttu-id="3468a-141">Bu nedenle ne zaman bir denetimin veri doğrulanmış?</span><span class="sxs-lookup"><span data-stu-id="3468a-141">So when does a control's data get validated?</span></span> <span data-ttu-id="3468a-142">Bu size, geliştirici bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="3468a-142">This is up to you, the developer.</span></span> <span data-ttu-id="3468a-143">Uygulamanızın gereksinimlerine bağlı olarak örtük veya açık doğrulama kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3468a-143">You can use either implicit or explicit validation, depending on the needs of your application.</span></span>  
  
#### <a name="implicit-validation"></a><span data-ttu-id="3468a-144">Örtük doğrulama</span><span class="sxs-lookup"><span data-stu-id="3468a-144">Implicit Validation</span></span>  
 <span data-ttu-id="3468a-145">Kullanıcı girerken örtük doğrulama yaklaşımı veri doğrular.</span><span class="sxs-lookup"><span data-stu-id="3468a-145">The implicit validation approach validates data as the user enters it.</span></span> <span data-ttu-id="3468a-146">Yaygın olarak kullanıcı bir denetim çıktığınızda giriş odağını alır ve diğerine taşır her basılı gibi anahtarları okuyarak bir denetim veya daha fazla veri girildiği şekilde veri doğrulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3468a-146">You can validate the data as the data is entered in a control by reading the keys as they are pressed, or more commonly whenever the user takes the input focus away from one control and moves to the next.</span></span> <span data-ttu-id="3468a-147">Bu yaklaşım, çalıştıkları gibi kullanıcı hemen veriler hakkında görüş istediğinizde yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="3468a-147">This approach is useful when you want to give the user immediate feedback about the data as they are working.</span></span>  
  
 <span data-ttu-id="3468a-148">Bir denetim için örtük doğrulama kullanmak istiyorsanız, bu denetimin ayarlamalısınız <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> özelliğine `true`.</span><span class="sxs-lookup"><span data-stu-id="3468a-148">If you want to use implicit validation for a control, you must set that control's <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> property to `true`.</span></span> <span data-ttu-id="3468a-149">İptal ederseniz <xref:System.Windows.Forms.Control.Validating> olay, Denetim davranışını, atanan değeri tarafından belirlenir <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>.</span><span class="sxs-lookup"><span data-stu-id="3468a-149">If you cancel the <xref:System.Windows.Forms.Control.Validating> event, the behavior of the control will be determined by what value that you assigned to <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>.</span></span> <span data-ttu-id="3468a-150">Size atanmış olması <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>, olay iptal edilirse <xref:System.Windows.Forms.Control.Validated> olay gerçekleşmez.</span><span class="sxs-lookup"><span data-stu-id="3468a-150">If you assigned <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>, canceling the event will cause the <xref:System.Windows.Forms.Control.Validated> event not to occur.</span></span> <span data-ttu-id="3468a-151">Kullanıcı verileri için geçerli bir giriş olana kadar giriş odağını geçerli denetiminde kalır.</span><span class="sxs-lookup"><span data-stu-id="3468a-151">Input focus will remain on the current control until the user changes the data to a valid input.</span></span> <span data-ttu-id="3468a-152">Size atanmış olması <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>, <xref:System.Windows.Forms.Control.Validated> olayı iptal eder, ancak odak hala sonraki denetime değiştirme olay gerçekleşmez.</span><span class="sxs-lookup"><span data-stu-id="3468a-152">If you assigned <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>, the <xref:System.Windows.Forms.Control.Validated> event will not occur when you cancel the event, but focus will still change to the next control.</span></span>  
  
 <span data-ttu-id="3468a-153">Atama <xref:System.Windows.Forms.AutoValidate.Disable> için <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> özelliği örtük doğrulama tamamen engeller.</span><span class="sxs-lookup"><span data-stu-id="3468a-153">Assigning <xref:System.Windows.Forms.AutoValidate.Disable> to the <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> property prevents implicit validation altogether.</span></span> <span data-ttu-id="3468a-154">Denetimleri doğrulamak için açık doğrulama kullanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="3468a-154">To validate your controls, you will have to use explicit validation.</span></span>  
  
#### <a name="explicit-validation"></a><span data-ttu-id="3468a-155">Açık doğrulama</span><span class="sxs-lookup"><span data-stu-id="3468a-155">Explicit Validation</span></span>  
 <span data-ttu-id="3468a-156">Açık doğrulama yaklaşım verileri bir kerede doğrular.</span><span class="sxs-lookup"><span data-stu-id="3468a-156">The explicit validation approach validates data at one time.</span></span> <span data-ttu-id="3468a-157">Kaydet düğmesine veya sonraki bir bağlantıya tıklayarak gibi bir kullanıcı eylemi yanıta verilerde doğrulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3468a-157">You can validate the data in response to a user action, such as clicking a Save button or a Next link.</span></span> <span data-ttu-id="3468a-158">Bir kullanıcı eylemi oluştuğunda aşağıdaki yollardan birinde açık doğrulama tetikleyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="3468a-158">When the user action occurs, you can trigger explicit validation in one of the following ways:</span></span>  
  
-   <span data-ttu-id="3468a-159">Çağrı <xref:System.Windows.Forms.ContainerControl.Validate%2A> odağını kaybetmiş son denetim doğrulanacak.</span><span class="sxs-lookup"><span data-stu-id="3468a-159">Call <xref:System.Windows.Forms.ContainerControl.Validate%2A> to validate the last control to have lost focus.</span></span>  
  
-   <span data-ttu-id="3468a-160">Çağrı <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> bir form veya kapsayıcı denetiminin tüm alt denetimleri doğrulamak için.</span><span class="sxs-lookup"><span data-stu-id="3468a-160">Call <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> to validate all child controls in a form or container control.</span></span>  
  
-   <span data-ttu-id="3468a-161">Denetimlerinde verileri el ile doğrulamak için özel bir yöntemini çağırın.</span><span class="sxs-lookup"><span data-stu-id="3468a-161">Call a custom method to validate the data in the controls manually.</span></span>  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a><span data-ttu-id="3468a-162">Varsayılan örtük doğrulama davranışını Windows Forms denetimleri</span><span class="sxs-lookup"><span data-stu-id="3468a-162">Default Implicit Validation Behavior for Windows Forms Controls</span></span>  
 <span data-ttu-id="3468a-163">Farklı Windows Forms denetimleri için farklı varsayılan ayarlar sahip kendi <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="3468a-163">Different Windows Forms controls have different defaults for their <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> property.</span></span> <span data-ttu-id="3468a-164">Aşağıdaki tabloda, en yaygın denetimleri ve varsayılanlarına gösterir.</span><span class="sxs-lookup"><span data-stu-id="3468a-164">The following table shows the most common controls and their defaults.</span></span>  
  
|<span data-ttu-id="3468a-165">Denetim</span><span class="sxs-lookup"><span data-stu-id="3468a-165">Control</span></span>|<span data-ttu-id="3468a-166">Varsayılan doğrulama davranışı</span><span class="sxs-lookup"><span data-stu-id="3468a-166">Default Validation Behavior</span></span>|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|<span data-ttu-id="3468a-167">Visual Studio'da gösterilmeyen özelliği</span><span class="sxs-lookup"><span data-stu-id="3468a-167">Property not exposed in Visual Studio</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="3468a-168">Visual Studio'da gösterilmeyen özelliği</span><span class="sxs-lookup"><span data-stu-id="3468a-168">Property not exposed in Visual Studio</span></span>|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a><span data-ttu-id="3468a-169">Formu kapatmadan ve doğrulama geçersiz kılma</span><span class="sxs-lookup"><span data-stu-id="3468a-169">Closing the Form and Overriding Validation</span></span>  
 <span data-ttu-id="3468a-170">İçerdiği verileri geçersiz olduğundan bir denetim odağı korur, Normal yollardan biriyle üst formu kapatmak mümkün değildir:</span><span class="sxs-lookup"><span data-stu-id="3468a-170">When a control maintains focus because the data it contains is invalid, it is impossible to close the parent form in one of the usual ways:</span></span>  
  
-   <span data-ttu-id="3468a-171">Tıklayarak **Kapat** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="3468a-171">By clicking the **Close** button.</span></span>  
  
-   <span data-ttu-id="3468a-172">Seçerek **Kapat** içinde **sistem** menüsü.</span><span class="sxs-lookup"><span data-stu-id="3468a-172">By selecting **Close** in the **System** menu.</span></span>  
  
-   <span data-ttu-id="3468a-173">Çağırarak <xref:System.Windows.Forms.Form.Close%2A> yöntemi programlı olarak.</span><span class="sxs-lookup"><span data-stu-id="3468a-173">By calling the <xref:System.Windows.Forms.Form.Close%2A> method programmatically.</span></span>  
  
 <span data-ttu-id="3468a-174">Ancak, bazı durumlarda, olup denetimleri geçerli değerler bağımsız olarak formu kapatmak kullanıcı izin vermek isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3468a-174">However, in some cases, you might want to let the user close the form regardless of whether the values in the controls are valid.</span></span> <span data-ttu-id="3468a-175">Doğrulama geçersiz kılabilir ve hala formun için bir işleyici oluşturarak geçersiz veri içeren bir formu kapatmak <xref:System.Windows.Forms.Form.Closing> olay.</span><span class="sxs-lookup"><span data-stu-id="3468a-175">You can override validation and close a form that still contains invalid data by creating a handler for the form's <xref:System.Windows.Forms.Form.Closing> event.</span></span> <span data-ttu-id="3468a-176">Olayda ayarlamak <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> özelliğine `false`.</span><span class="sxs-lookup"><span data-stu-id="3468a-176">In the event, set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property to `false`.</span></span> <span data-ttu-id="3468a-177">Bu, formu kapatmak için zorlar.</span><span class="sxs-lookup"><span data-stu-id="3468a-177">This forces the form to close.</span></span> <span data-ttu-id="3468a-178">Daha fazla bilgi ve bir örnek için bkz: <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3468a-178">For more information and an example, see <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3468a-179">Bu şekilde kapatmak için form zorlarsanız, formun denetimlerinde zaten kaydedilmemiş verileri kaybolur.</span><span class="sxs-lookup"><span data-stu-id="3468a-179">If you force the form to close in this manner, any data in the form's controls that has not already been saved is lost.</span></span> <span data-ttu-id="3468a-180">Buna ek olarak, bunlar kapatıldığında kalıcı formları denetimleri içeriğini doğrulamaz.</span><span class="sxs-lookup"><span data-stu-id="3468a-180">In addition, modal forms do not validate the contents of controls when they are closed.</span></span> <span data-ttu-id="3468a-181">Denetim odağı kilitlemek için denetim doğrulama kullanmaya devam edebilirsiniz, ancak formu kapatmadan ile ilişkilendirilmiş davranışı hakkında endişelenmeniz gerekmez.</span><span class="sxs-lookup"><span data-stu-id="3468a-181">You can still use control validation to lock focus to a control, but you do not have to be concerned about the behavior associated with closing the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3468a-182">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3468a-182">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
 <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType>  
 [<span data-ttu-id="3468a-183">MaskedTextBox denetimi</span><span class="sxs-lookup"><span data-stu-id="3468a-183">MaskedTextBox Control</span></span>](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)  
 [<span data-ttu-id="3468a-184">Normal ifade örnekleri</span><span class="sxs-lookup"><span data-stu-id="3468a-184">Regular Expression Examples</span></span>](../../../docs/standard/base-types/regular-expression-examples.md)