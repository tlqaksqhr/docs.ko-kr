---
title: 사용자 지정 컨트롤에 대한 응용 프로그램 설정
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
ms.openlocfilehash: 46300f679471874ac5046d0a1077d8abca57f2c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518566"
---
# <a name="application-settings-for-custom-controls"></a><span data-ttu-id="a6efd-102">사용자 지정 컨트롤에 대한 응용 프로그램 설정</span><span class="sxs-lookup"><span data-stu-id="a6efd-102">Application Settings for Custom Controls</span></span>
<span data-ttu-id="a6efd-103">사용자 지정 컨트롤 컨트롤 공급 업체 응용 프로그램에서 호스팅되는 응용 프로그램 설정을 유지 하는 기능을 제공 하려면 특정 작업을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-103">You must complete certain tasks to give your custom controls the ability to persist application settings when the controls are hosted in third-party applications.</span></span>  
  
 <span data-ttu-id="a6efd-104">대부분의 응용 프로그램 설정 기능에 대 한 설명서는 독립 실행형 응용 프로그램을 만들고 있다는 가정 아래에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-104">Most of the documentation about the Application Settings feature is written under the assumption that you are creating a standalone application.</span></span> <span data-ttu-id="a6efd-105">그러나 응용 프로그램에서 다른 개발자가 호스트 하는 컨트롤을 만드는 경우 해야 해당 설정을 유지 하기 위해 컨트롤에 대 한 몇 가지 추가 단계가 제대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-105">However, if you are creating a control that other developers will host in their applications, you need to take a few additional steps for your control to persist its settings properly.</span></span>  
  
## <a name="application-settings-and-custom-controls"></a><span data-ttu-id="a6efd-106">응용 프로그램 설정 및 사용자 지정 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a6efd-106">Application Settings and Custom Controls</span></span>  
 <span data-ttu-id="a6efd-107">제대로 해당 설정을 유지 하기 위해 컨트롤에 대 한 프로세스 자체 전용된 응용 프로그램 설정 래퍼 클래스에서 파생 된 만들어 캡슐화 해야 것 <xref:System.Configuration.ApplicationSettingsBase>합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-107">For your control to properly persist its settings, it must encapsulate the process by creating its own dedicated applications settings wrapper class, derived from <xref:System.Configuration.ApplicationSettingsBase>.</span></span> <span data-ttu-id="a6efd-108">또한 주 제어 클래스 구현 해야 합니다는 <xref:System.Configuration.IPersistComponentSettings>합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-108">Additionally, the main control class must implement the <xref:System.Configuration.IPersistComponentSettings>.</span></span> <span data-ttu-id="a6efd-109">인터페이스에는 두 가지 방법 뿐 아니라 여러 속성이 포함 되어 <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 및 <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-109">The interface contains several properties as well as two methods, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> and <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>.</span></span> <span data-ttu-id="a6efd-110">사용 하 여 폼에 컨트롤을 추가 하는 경우는 **Windows Forms 디자이너** Visual Studio에서는 Windows Forms 호출 <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 컨트롤을 초기화할 경우에 자동으로 호출 해야 합니다. <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> 에서 직접는 `Dispose` 컨트롤의 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-110">If you add your control to a form using the **Windows Forms Designer** in Visual Studio, Windows Forms will call <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automatically when the control is initialized; you must call <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> yourself in the `Dispose` method of your control.</span></span>  
  
 <span data-ttu-id="a6efd-111">또한 Visual Studio와 같은 디자인 타임 환경에서 제대로 작동 하려면 사용자 지정 컨트롤에 대 한 응용 프로그램 설정에 대 한 순서에는 다음을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-111">In addition, you should implement the following in order for application settings for custom controls to work properly in design-time environments such as Visual Studio:</span></span>  
  
1.  <span data-ttu-id="a6efd-112">생성자를 사용 하는 사용자 지정 응용 프로그램 설정 클래스는 <xref:System.ComponentModel.IComponent> 단일 매개 변수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-112">A custom application settings class with a constructor that takes an <xref:System.ComponentModel.IComponent> as a single parameter.</span></span> <span data-ttu-id="a6efd-113">이 클래스를 사용 하 여 저장 하 고 모든 응용 프로그램 설정을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-113">Use this class to save and load all of your application settings.</span></span> <span data-ttu-id="a6efd-114">이 클래스의 새 인스턴스를 만들 때 생성자를 사용 하 여 사용자 지정 컨트롤을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-114">When you create a new instance of this class, pass your custom control using the constructor.</span></span>  
  
2.  <span data-ttu-id="a6efd-115">컨트롤 생성 되 고과 같은 폼의 폼에 배치 된 후이 사용자 지정 설정 클래스를 만들 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-115">Create this custom settings class after the control has been created and placed on a form, such as in the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
 <span data-ttu-id="a6efd-116">사용자 지정 설정 클래스를 만드는 방법에 지침은 [하는 방법: 응용 프로그램 설정 만들기](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-116">For instructions on creating a custom settings class, see [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).</span></span>  
  
## <a name="settings-keys-and-shared-settings"></a><span data-ttu-id="a6efd-117">설정 키 및 공유 설정</span><span class="sxs-lookup"><span data-stu-id="a6efd-117">Settings Keys and Shared Settings</span></span>  
 <span data-ttu-id="a6efd-118">일부 컨트롤은 동일한 폼 내에서 여러 번 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-118">Some controls can be used multiple times within the same form.</span></span> <span data-ttu-id="a6efd-119">대부분의 경우 이러한 컨트롤을 개별 설정을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-119">Most of the time, you will want these controls to persist their own individual settings.</span></span> <span data-ttu-id="a6efd-120">와 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 속성 <xref:System.Configuration.IPersistComponentSettings>, 여러 버전의 폼에 컨트롤을 명확 하 게 되는 고유 문자열을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-120">With the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> property on <xref:System.Configuration.IPersistComponentSettings>, you can supply a unique string that acts to disambiguate multiple versions of a control on a form.</span></span>  
  
 <span data-ttu-id="a6efd-121">구현 하는 가장 간단한 방법은 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 사용 하는 것은 <xref:System.Windows.Forms.Control.Name%2A> 에 대 한 컨트롤의 속성은 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-121">The simplest way to implement <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> is to use the <xref:System.Windows.Forms.Control.Name%2A> property of the control for the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>.</span></span> <span data-ttu-id="a6efd-122">값을 전달 로드 하거나 컨트롤의 설정을 저장할 때 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 에 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 의 속성은 <xref:System.Configuration.ApplicationSettingsBase> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-122">When you load or save the control's settings, you pass the value of <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> on to the <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> property of the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span> <span data-ttu-id="a6efd-123">사용자의 설정을 XML 유지 하는 경우이 고유 키를 사용 하는 응용 프로그램 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-123">Application Settings uses this unique key when it persists the user's settings to XML.</span></span> <span data-ttu-id="a6efd-124">다음 코드 예제와 어떻게는 `<userSettings>` 섹션 이라는 사용자 지정 컨트롤의 인스턴스를 찾는 `CustomControl1` 에 대 한 설정을 저장 하는 `Text` 속성.</span><span class="sxs-lookup"><span data-stu-id="a6efd-124">The following code example shows how a `<userSettings>` section may look for an instance of a custom control named `CustomControl1` that saves a setting for its `Text` property.</span></span>  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 <span data-ttu-id="a6efd-125">에 대 한 값을 제공 하지 않는 컨트롤의 모든 인스턴스가 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 동일한 설정을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6efd-125">Any instances of a control that do not supply a value for <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> will share the same settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6efd-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6efd-126">See Also</span></span>  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.IPersistComponentSettings>  
 [<span data-ttu-id="a6efd-127">응용 프로그램 설정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="a6efd-127">Application Settings Architecture</span></span>](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)
