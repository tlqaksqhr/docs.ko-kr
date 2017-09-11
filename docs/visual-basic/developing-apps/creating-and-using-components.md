---
title: "Visual Basic에서 구성 요소 만들기 및 사용"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- components [Visual Basic]
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 03929dd0dbb81a9efee5b69ede78ff0b4ab4d380
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="creating-and-using-components-in-visual-basic"></a><span data-ttu-id="fff4c-102">Visual Basic에서 구성 요소 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="fff4c-102">Creating and Using Components in Visual Basic</span></span>
<span data-ttu-id="fff4c-103">*구성 요소*는 <xref:System.ComponentModel.IComponent?displayProperty=fullName> 인터페이스를 구현하는 클래스이거나 <xref:System.ComponentModel.IComponent>를 구현하는 클래스에서 직접 또는 간접적으로 파생되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-103">A *component* is a class that implements the <xref:System.ComponentModel.IComponent?displayProperty=fullName> interface or that derives directly or indirectly from a class that implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="fff4c-104">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 구성 요소는 재사용 가능한 개체이고, 다른 개체와 상호 작용할 수 있으며, 외부 리소스 및 디자인 타임 지원에 대한 제어를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-104">A [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] component is an object that is reusable, can interact with other objects, and provides control over external resources and design-time support.</span></span>  
  
 <span data-ttu-id="fff4c-105">구성 요소의 중요한 기능은 구성 요소가 디자인 가능하다는 것입니다. 즉, 구성 요소인 클래스는 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 통합 개발 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-105">An important feature of components is that they are designable, which means that a class that is a component can be used in the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Integrated Development Environment.</span></span> <span data-ttu-id="fff4c-106">구성 요소는 도구 상자에 추가하고, 양식에 끌어서 놓고, 디자인 화면에서 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-106">A component can be added to the Toolbox, dragged and dropped onto a form, and manipulated on a design surface.</span></span> <span data-ttu-id="fff4c-107">구성 요소에 대한 기본 디자인 타임 지원은 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]에 기본 제공됩니다. 구성 요소 개발자는 기본 디자인 타임 기능을 이용하기 위해 추가 작업을 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-107">Notice that base design-time support for components is built into the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]; a component developer does not have to do any additional work to take advantage of the base design-time functionality.</span></span>  
  
 <span data-ttu-id="fff4c-108">*컨트롤*과 구성 요소는 둘 다 디자인 가능하다는 점에서 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-108">A *control* is similar to a component, as both are designable.</span></span> <span data-ttu-id="fff4c-109">그러나 컨트롤은 사용자 인터페이스를 제공하지만 구성 요소는 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-109">However, a control provides a user interface, while a component does not.</span></span> <span data-ttu-id="fff4c-110">컨트롤은 기본 컨트롤 클래스인 <xref:System.Windows.Forms.Control> 또는 <xref:System.Web.UI.Control> 중 하나에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-110">A control must derive from one of the base control classes: <xref:System.Windows.Forms.Control> or <xref:System.Web.UI.Control>.</span></span>  
  
## <a name="when-to-create-a-component"></a><span data-ttu-id="fff4c-111">구성 요소를 만들어야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="fff4c-111">When to Create a Component</span></span>  
 <span data-ttu-id="fff4c-112">클래스가 Design Surface(예: Windows Forms 또는 Web Forms 디자이너)에서 사용되지만 사용자 인터페이스가 없는 경우 클래스는 구성 요소로서, <xref:System.ComponentModel.IComponent>를 구현하거나 <xref:System.ComponentModel.IComponent>를 직접 또는 간접적으로 구현하는 클래스에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-112">If your class will be used on a design surface (such as the Windows Forms or Web Forms Designer) but has no user interface, it should be a component and implement <xref:System.ComponentModel.IComponent>, or derive from a class that directly or indirectly implements <xref:System.ComponentModel.IComponent>.</span></span>  
  
 <span data-ttu-id="fff4c-113"><xref:System.ComponentModel.Component> 및 <xref:System.ComponentModel.MarshalByValueComponent> 클래스는 <xref:System.ComponentModel.IComponent> 인터페이스의 기본 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-113">The <xref:System.ComponentModel.Component> and <xref:System.ComponentModel.MarshalByValueComponent> classes are base implementations of the <xref:System.ComponentModel.IComponent> interface.</span></span> <span data-ttu-id="fff4c-114">이러한 클래스 간의 기본 차이점은 <xref:System.ComponentModel.Component> 클래스는 참조에 의해 마샬링되지만 <xref:System.ComponentModel.IComponent>는 값에 의해 마샬링된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-114">The main difference between these classes is that the <xref:System.ComponentModel.Component> class is marshaled by reference, while <xref:System.ComponentModel.IComponent> is marshaled by value.</span></span> <span data-ttu-id="fff4c-115">다음 목록에서는 구현에 대한 다양한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-115">The following list provides broad guidelines for implementers.</span></span>  
  
-   <span data-ttu-id="fff4c-116">구성 요소가 참조에 의해 마샬링되어야 하는 경우 <xref:System.ComponentModel.Component>에서 파생합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-116">If your component needs to be marshaled by reference, derive from <xref:System.ComponentModel.Component>.</span></span>  
  
-   <span data-ttu-id="fff4c-117">구성 요소가 값에 의해 마샬링되어야 하는 경우 <xref:System.ComponentModel.MarshalByValueComponent>에서 파생합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-117">If your component needs to be marshaled by value, derive from <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
-   <span data-ttu-id="fff4c-118">단일 상속으로 인해 구성 요소가 기본 구현 중 하나에서 파생될 수 없는 경우 <xref:System.ComponentModel.IComponent>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-118">If your component cannot derive from one of the base implementations due to single inheritance, implement <xref:System.ComponentModel.IComponent>.</span></span>  
  
 <span data-ttu-id="fff4c-119">디자인 타임 지원에 대한 자세한 내용은 [구성 요소의 디자인 타임 특성](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3) 및 [디자인 타임 지원 확장](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fff4c-119">For more information about design-time support, see [Design-Time Attributes for Components](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3) and [Extending Design-Time Support](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2).</span></span>  
  
## <a name="component-classes"></a><span data-ttu-id="fff4c-120">구성 요소 클래스</span><span class="sxs-lookup"><span data-stu-id="fff4c-120">Component Classes</span></span>  
 <span data-ttu-id="fff4c-121"><xref:System.ComponentModel> 네임스페이스는 구성 요소와 컨트롤의 런타임 및 디자인 타임 동작을 구현하는 데 사용되는 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-121">The <xref:System.ComponentModel> namespace provides classes that are used to implement the run-time and design-time behavior of components and controls.</span></span> <span data-ttu-id="fff4c-122">이 네임스페이스에는 특성 및 형식 변환기를 구현하고, 데이터 소스에 바인딩하고, 구성 요소 사용을 허가하기 위한 기본 클래스 및 인터페이스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-122">This namespace includes the base classes and interfaces for implementing attributes and type converters, binding to data sources, and licensing components.</span></span>  
  
 <span data-ttu-id="fff4c-123">핵심 구성 요소 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-123">The core component classes are:</span></span>  
  
-   <span data-ttu-id="fff4c-124"><xref:System.ComponentModel.Component>.</span><span class="sxs-lookup"><span data-stu-id="fff4c-124"><xref:System.ComponentModel.Component>.</span></span> <span data-ttu-id="fff4c-125"><xref:System.ComponentModel.IComponent> 인터페이스에 대한 기본 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-125">A base implementation for the <xref:System.ComponentModel.IComponent> interface.</span></span> <span data-ttu-id="fff4c-126">이 클래스를 통해 응용 프로그램 간에 개체를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-126">This class enables object sharing between applications.</span></span>  
  
-   <span data-ttu-id="fff4c-127"><xref:System.ComponentModel.MarshalByValueComponent>.</span><span class="sxs-lookup"><span data-stu-id="fff4c-127"><xref:System.ComponentModel.MarshalByValueComponent>.</span></span> <span data-ttu-id="fff4c-128"><xref:System.ComponentModel.IComponent> 인터페이스에 대한 기본 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-128">A base implementation for the <xref:System.ComponentModel.IComponent> interface.</span></span>  
  
-   <span data-ttu-id="fff4c-129"><xref:System.ComponentModel.Container>.</span><span class="sxs-lookup"><span data-stu-id="fff4c-129"><xref:System.ComponentModel.Container>.</span></span> <span data-ttu-id="fff4c-130"><xref:System.ComponentModel.IContainer> 인터페이스에 대한 기본 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-130">The base implementation for the <xref:System.ComponentModel.IContainer> interface.</span></span> <span data-ttu-id="fff4c-131">이 클래스는 0 또는 추가 구성 요소를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-131">This class encapsulates zero or more components.</span></span>  
  
 <span data-ttu-id="fff4c-132">구성 요소 라이선싱에 사용되는 일부 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-132">Some of the classes used for component licensing are:</span></span>  
  
-   <span data-ttu-id="fff4c-133"><xref:System.ComponentModel.License>.</span><span class="sxs-lookup"><span data-stu-id="fff4c-133"><xref:System.ComponentModel.License>.</span></span> <span data-ttu-id="fff4c-134">모든 라이선스에 대한 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-134">The abstract base class for all licenses.</span></span> <span data-ttu-id="fff4c-135">라이선스는 구성 요소의 특정 인스턴스에 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-135">A license is granted to a specific instance of a component.</span></span>  
  
-   <span data-ttu-id="fff4c-136"><xref:System.ComponentModel.LicenseManager>.</span><span class="sxs-lookup"><span data-stu-id="fff4c-136"><xref:System.ComponentModel.LicenseManager>.</span></span> <span data-ttu-id="fff4c-137">라이선스를 구성 요소에 추가하고 <xref:System.ComponentModel.LicenseProvider>를 관리하기 위한 속성과 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-137">Provides properties and methods to add a license to a component and to manage a <xref:System.ComponentModel.LicenseProvider>.</span></span>  
  
-   <span data-ttu-id="fff4c-138"><xref:System.ComponentModel.LicenseProvider>.</span><span class="sxs-lookup"><span data-stu-id="fff4c-138"><xref:System.ComponentModel.LicenseProvider>.</span></span> <span data-ttu-id="fff4c-139">라이선스 공급자를 구현하기 위한 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-139">The abstract base class for implementing a license provider.</span></span>  
  
-   <span data-ttu-id="fff4c-140"><xref:System.ComponentModel.LicenseProviderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fff4c-140"><xref:System.ComponentModel.LicenseProviderAttribute>.</span></span> <span data-ttu-id="fff4c-141">클래스와 함께 사용할 <xref:System.ComponentModel.LicenseProvider> 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-141">Specifies the <xref:System.ComponentModel.LicenseProvider> class to use with a class.</span></span>  
  
 <span data-ttu-id="fff4c-142">구성 요소를 설명 및 유지하는 데 일반적으로 사용되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-142">Classes commonly used for describing and persisting components.</span></span>  
  
-   <span data-ttu-id="fff4c-143"><xref:System.ComponentModel.TypeDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="fff4c-143"><xref:System.ComponentModel.TypeDescriptor>.</span></span> <span data-ttu-id="fff4c-144">구성 요소의 특성, 속성 및 이벤트와 같이, 구성 요소의 특성에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-144">Provides information about the characteristics for a component, such as its attributes, properties, and events.</span></span>  
  
-   <span data-ttu-id="fff4c-145"><xref:System.ComponentModel.EventDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="fff4c-145"><xref:System.ComponentModel.EventDescriptor>.</span></span> <span data-ttu-id="fff4c-146">이벤트에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-146">Provides information about an event.</span></span>  
  
-   <span data-ttu-id="fff4c-147"><xref:System.ComponentModel.PropertyDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="fff4c-147"><xref:System.ComponentModel.PropertyDescriptor>.</span></span> <span data-ttu-id="fff4c-148">속성에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-148">Provides information about a property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fff4c-149">관련 단원</span><span class="sxs-lookup"><span data-stu-id="fff4c-149">Related Sections</span></span>  
 [<span data-ttu-id="fff4c-150">클래스, 구성 요소 및 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fff4c-150">Class vs. Component vs. Control</span></span>](http://msdn.microsoft.com/library/db8b842e-44d9-40cc-a0f8-70fd189632c3)  
 <span data-ttu-id="fff4c-151">*구성 요소* 및 *컨트롤*을 정의하고 이들 항목과 클래스 간의 차이점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-151">Defines *component* and *control*, and discusses the differences between them and classes.</span></span>  
  
 [<span data-ttu-id="fff4c-152">구성 요소 제작</span><span class="sxs-lookup"><span data-stu-id="fff4c-152">Component Authoring</span></span>](http://msdn.microsoft.com/library/4a5a5e49-0378-4a31-83bc-24da0f1a727d)  
 <span data-ttu-id="fff4c-153">구성 요소를 시작하기 위한 로드맵입니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-153">Roadmap for getting started with components.</span></span>  
  
 [<span data-ttu-id="fff4c-154">구성 요소 제작 연습</span><span class="sxs-lookup"><span data-stu-id="fff4c-154">Component Authoring Walkthroughs</span></span>](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)  
 <span data-ttu-id="fff4c-155">구성 요소 프로그래밍에 대한 단계별 지침을 제공하는 항목의 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-155">Links to topics that provide step-by-step instruction for component programming.</span></span>  
  
 [<span data-ttu-id="fff4c-156">구성 요소 클래스</span><span class="sxs-lookup"><span data-stu-id="fff4c-156">Component Classes</span></span>](http://msdn.microsoft.com/library/ce2e5647-e673-4c2b-8125-ffebbd9d71bc)  
 <span data-ttu-id="fff4c-157">클래스를 구성 요소로 설정하는 작업, 구성 요소 기능을 표시하는 방법, 구성 요소에 대한 액세스 제어 및 구성 요소 인스턴스를 만드는 방법 제어를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-157">Describes what makes a class a component, ways to expose component functionality, controlling access to components, and controlling how component instances are created.</span></span>  
  
 [<span data-ttu-id="fff4c-158">컨트롤 및 구성 요소 제작 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fff4c-158">Troubleshooting Control and Component Authoring</span></span>](../../framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 <span data-ttu-id="fff4c-159">일반적인 문제 해결 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fff4c-159">Explains how to fix common problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fff4c-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fff4c-160">See Also</span></span>  
 <span data-ttu-id="fff4c-161">[방법: Windows Forms에서 디자인 타임 지원 액세스](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09) </span><span class="sxs-lookup"><span data-stu-id="fff4c-161">[How to: Access Design-Time Support in Windows Forms](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09) </span></span>  
 <span data-ttu-id="fff4c-162">[방법: 디자인 모드에서 컨트롤의 모양과 동작 확장](http://msdn.microsoft.com/library/68f85054-2253-47f5-a4f2-3f1ac8c9f27b) </span><span class="sxs-lookup"><span data-stu-id="fff4c-162">[How to: Extend the Appearance and Behavior of Controls in Design Mode](http://msdn.microsoft.com/library/68f85054-2253-47f5-a4f2-3f1ac8c9f27b) </span></span>  
 [<span data-ttu-id="fff4c-163">방법: 디자인 모드에서 컨트롤에 대한 사용자 지정 초기화 수행</span><span class="sxs-lookup"><span data-stu-id="fff4c-163">How to: Perform Custom Initialization for Controls in Design Mode</span></span>](http://msdn.microsoft.com/library/914eaa03-092f-4556-9160-b8a2a40641d9)

