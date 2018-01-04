---
title: "방법: 응용 프로그램 설정 만들기"
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
helpviewer_keywords:
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], creating
ms.assetid: 1e7aa347-af75-41e5-89ca-f53cab704f72
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6d0ede88d8f9b4c15cd3e0f141870b9a5e747aa9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-application-settings"></a><span data-ttu-id="7d2c8-102">방법: 응용 프로그램 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="7d2c8-102">How to: Create Application Settings</span></span>
<span data-ttu-id="7d2c8-103">관리 코드를 사용하여 새 응용 프로그램 설정을 만들고, 이러한 설정이 런타임에 자동으로 로드 및 저장되도록 폼의 속성이나 폼의 컨트롤에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-103">Using managed code, you can create new application settings and bind them to properties on your form or your form's controls, so that these settings are loaded and saved automatically at run time.</span></span>  
  
 <span data-ttu-id="7d2c8-104">다음 절차에서는 <xref:System.Configuration.ApplicationSettingsBase>에서 파생되는 래퍼 클래스를 수동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-104">In the following procedure, you manually create a wrapper class that derives from <xref:System.Configuration.ApplicationSettingsBase>.</span></span> <span data-ttu-id="7d2c8-105">노출하려는 각 응용 프로그램 설정에 대한 공개적으로 액세스 가능한 속성을 이 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-105">To this class you add a publicly accessible property for each application setting that you want to expose.</span></span>  
  
 <span data-ttu-id="7d2c8-106">Visual Studio 디자이너에서 최소한의 코드로 이 절차를 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-106">You can also perform this procedure using minimal code in the Visual Studio designer.</span></span>  <span data-ttu-id="7d2c8-107">참조도 [하는 방법: 응용 프로그램 설정을 사용 하 여 작성 디자이너](http://msdn.microsoft.com/library/wabtadw6\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-107">Also see [How to: Create Application Settings Using the Designer](http://msdn.microsoft.com/library/wabtadw6\(v=vs.110\)).</span></span>  
  
### <a name="to-create-new-application-settings-programmatically"></a><span data-ttu-id="7d2c8-108">새 응용 프로그램 설정을 프로그래밍 방식으로 만들려면</span><span class="sxs-lookup"><span data-stu-id="7d2c8-108">To create new Application Settings programmatically</span></span>  
  
1.  <span data-ttu-id="7d2c8-109">프로젝트에 새 클래스를 추가하고 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-109">Add a new class to your project, and rename it.</span></span> <span data-ttu-id="7d2c8-110">이 절차에서는이 클래스 라고 합니다 `MyUserSettings`합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-110">For this procedure, we will call this class `MyUserSettings`.</span></span> <span data-ttu-id="7d2c8-111">클래스가 <xref:System.Configuration.ApplicationSettingsBase>에서 파생되도록 클래스 정의를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-111">Change the class definition so that the class derives from <xref:System.Configuration.ApplicationSettingsBase>.</span></span>  
  
2.  <span data-ttu-id="7d2c8-112">필요한 각 응용 프로그램 설정에 대해 이 래퍼 클래스의 속성을 정의하고 설정의 범위에 따라 해당 속성을 <xref:System.Configuration.ApplicationScopedSettingAttribute> 또는 <xref:System.Configuration.UserScopedSettingAttribute>로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-112">Define a property on this wrapper class for each application setting you require, and apply that property with either the <xref:System.Configuration.ApplicationScopedSettingAttribute> or <xref:System.Configuration.UserScopedSettingAttribute>, depending on the scope of the setting.</span></span> <span data-ttu-id="7d2c8-113">설정 범위에 대 한 자세한 내용은 참조 [응용 프로그램 설정 개요](../../../../docs/framework/winforms/advanced/application-settings-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-113">For more information about settings scope, see [Application Settings Overview](../../../../docs/framework/winforms/advanced/application-settings-overview.md).</span></span> <span data-ttu-id="7d2c8-114">지금까지 작성된 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-114">By now, your code should look like this:</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
     [!code-vb[ApplicationSettings.Create#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
3.  <span data-ttu-id="7d2c8-115">응용 프로그램에서 이 래퍼 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-115">Create an instance of this wrapper class in your application.</span></span> <span data-ttu-id="7d2c8-116">일반적으로 기본 폼의 전용 멤버가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-116">It will commonly be a private member of the main form.</span></span> <span data-ttu-id="7d2c8-117">이제 클래스를 정의했으므로 속성(이 경우 폼의 <xref:System.Windows.Forms.Form.BackColor%2A> 속성)에 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-117">Now that you have defined your class, you need to bind it to a property; in this case, the <xref:System.Windows.Forms.Form.BackColor%2A> property of your form.</span></span> <span data-ttu-id="7d2c8-118">폼의에이 수행할 수 있습니다 `Load` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-118">You can accomplish this in your form's `Load` event handler.</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#2)]
     [!code-vb[ApplicationSettings.Create#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#2)]  
  
4.  <span data-ttu-id="7d2c8-119">런타임에 설정을 변경하는 방법을 제공하는 경우 폼을 닫을 때 사용자의 현재 설정을 디스크에 저장해야 합니다. 그러지 않으면 이러한 변경 내용이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-119">If you provide a way to change settings at run time, you will need to save the user's current settings to disk when your form closes, or else these changes will be lost.</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#3)]
     [!code-vb[ApplicationSettings.Create#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#3)]  
  
     <span data-ttu-id="7d2c8-120">이제 성공적으로 새 응용 프로그램 설정을 만들고 지정된 속성에 바인딩했습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-120">You have now successfully created a new application setting and bound it to the specified property.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7d2c8-121">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="7d2c8-121">.NET Framework Security</span></span>  
 <span data-ttu-id="7d2c8-122">기본 설정 공급자인 <xref:System.Configuration.LocalFileSettingsProvider>는 정보를 구성 파일에 일반 텍스트로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-122">The default settings provider, <xref:System.Configuration.LocalFileSettingsProvider>, persists information to configuration files as plain text.</span></span> <span data-ttu-id="7d2c8-123">이 경우 보안이 운영 체제에서 현재 사용자에 대해 제공하는 파일 액세스 보안으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-123">This limits security to the file access security provided by the operating system for the current user.</span></span> <span data-ttu-id="7d2c8-124">이 때문에 구성 파일에 정보를 저장할 때는 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-124">Because of this, care must be taken with the information stored in configuration files.</span></span> <span data-ttu-id="7d2c8-125">예를 들어 응용 프로그램 설정은 일반적으로 응용 프로그램의 데이터 저장소를 가리키는 연결 문자열을 저장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-125">For example, one common use for application settings is to store connection strings that point to the application's data store.</span></span> <span data-ttu-id="7d2c8-126">그러나 보안 문제 때문에 이러한 문자열은 암호를 포함하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-126">However, because of security concerns, such strings should not include passwords.</span></span> <span data-ttu-id="7d2c8-127">연결 문자열에 대한 자세한 내용은 <xref:System.Configuration.SpecialSetting>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2c8-127">For more information about connection strings, see <xref:System.Configuration.SpecialSetting>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d2c8-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d2c8-128">See Also</span></span>  
 <xref:System.Configuration.SpecialSettingAttribute>  
 <xref:System.Configuration.LocalFileSettingsProvider>  
 [<span data-ttu-id="7d2c8-129">응용 프로그램 설정 개요</span><span class="sxs-lookup"><span data-stu-id="7d2c8-129">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [<span data-ttu-id="7d2c8-130">방법: 응용 프로그램 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="7d2c8-130">How to: Validate Application Settings</span></span>](../../../../docs/framework/winforms/advanced/how-to-validate-application-settings.md)
