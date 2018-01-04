---
title: "Windows Forms 컨트롤의 속성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8d645a321319bf54ca0cc4f142c343420eb1f30e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="properties-in-windows-forms-controls"></a><span data-ttu-id="08ac2-102">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="08ac2-102">Properties in Windows Forms Controls</span></span>
<span data-ttu-id="08ac2-103">Windows Forms 컨트롤 속성 폼을 여러 기본 클래스를 상속 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-103">A Windows Forms control inherits many properties form the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="08ac2-104">여기에 속성 같은 <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>, 및 다른 많은 요인을 합니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-104">These include properties such as <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>, and many others.</span></span> <span data-ttu-id="08ac2-105">상속 된 속성에 대 한 세부 정보를 참조 하십시오. <xref:System.Windows.Forms.Control?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-105">For details about inherited properties, see <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="08ac2-106">컨트롤에서 상속된 속성을 재정의하고 새 속성을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-106">You can override inherited properties in your control as well as define new properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="08ac2-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="08ac2-107">In This Section</span></span>  
 [<span data-ttu-id="08ac2-108">속성 정의</span><span class="sxs-lookup"><span data-stu-id="08ac2-108">Defining a Property</span></span>](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 <span data-ttu-id="08ac2-109">사용자 지정 컨트롤 또는 구성 요소에 대한 속성을 구현하는 방법 및 속성을 디자인 환경으로 통합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-109">Shows how to implement a property for a custom control or component and shows how to integrate the property into the design environment.</span></span>  
  
 [<span data-ttu-id="08ac2-110">ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의</span><span class="sxs-lookup"><span data-stu-id="08ac2-110">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 <span data-ttu-id="08ac2-111">사용자 지정 컨트롤 또는 구성 요소에 대한 기본 속성 값을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-111">Shows how to define default property values for a custom control or component.</span></span>  
  
 [<span data-ttu-id="08ac2-112">속성 변경 이벤트</span><span class="sxs-lookup"><span data-stu-id="08ac2-112">Property-Changed Events</span></span>](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 <span data-ttu-id="08ac2-113">속성 값이 변경될 때 속성 변경 알림을 활성화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-113">Describes how to enable property-change notifications when a property value changes.</span></span>  
  
 [<span data-ttu-id="08ac2-114">방법: 구성 요소 컨트롤의 속성 노출</span><span class="sxs-lookup"><span data-stu-id="08ac2-114">How to: Expose Properties of Constituent Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)  
 <span data-ttu-id="08ac2-115">사용자 지정 복합 컨트롤에서 구성 요소 컨트롤의 속성을 노출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-115">Shows how to expose properties of constituent controls in a custom composite control.</span></span>  
  
 [<span data-ttu-id="08ac2-116">사용자 지정 컨트롤에서 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="08ac2-116">Method Implementation in Custom Controls</span></span>](../../../../docs/framework/winforms/controls/method-implementation-in-custom-controls.md)  
 <span data-ttu-id="08ac2-117">사용자 지정 컨트롤 및 구성 요소에서 메서드를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-117">Describes how to implement methods in custom controls and components.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="08ac2-118">참조</span><span class="sxs-lookup"><span data-stu-id="08ac2-118">Reference</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="08ac2-119">복합 컨트롤을 구현하기 위한 기본 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-119">Documents the base class for implementing composite controls.</span></span>  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 <span data-ttu-id="08ac2-120">지정 하는 특성에 설명 된 <xref:System.ComponentModel.TypeConverter> 사용자 지정 속성 형식에 대해 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-120">Documents the attribute that specifies the <xref:System.ComponentModel.TypeConverter> to use for a custom property type.</span></span>  
  
 <xref:System.ComponentModel.EditorAttribute>  
 <span data-ttu-id="08ac2-121">지정 하는 특성에 설명 된 <xref:System.Drawing.Design.UITypeEditor> 사용자 지정 속성에 사용할 합니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-121">Documents the attribute that specifies the <xref:System.Drawing.Design.UITypeEditor> to use for a custom property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="08ac2-122">관련 단원</span><span class="sxs-lookup"><span data-stu-id="08ac2-122">Related Sections</span></span>  
 [<span data-ttu-id="08ac2-123">Windows Forms 컨트롤의 특성</span><span class="sxs-lookup"><span data-stu-id="08ac2-123">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="08ac2-124">사용자 지정 컨트롤 및 구성 요소의 속성이나 다른 멤버에 적용할 수 있는 특성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-124">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 [<span data-ttu-id="08ac2-125">구성 요소의 디자인 타임 특성</span><span class="sxs-lookup"><span data-stu-id="08ac2-125">Design-Time Attributes for Components</span></span>](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)  
 <span data-ttu-id="08ac2-126">비주얼 디자이너에서 디자인 타임에 올바르게 표시되도록 구성 요소 및 컨트롤에 적용할 메타데이터 특성을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-126">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 [<span data-ttu-id="08ac2-127">디자인 타임 지원 확장</span><span class="sxs-lookup"><span data-stu-id="08ac2-127">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 <span data-ttu-id="08ac2-128">디자인 타임 지원을 제공하는 편집기 및 디자이너와 같은 클래스를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08ac2-128">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>
