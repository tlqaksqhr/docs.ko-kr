---
title: "방법: Windows Forms 컨트롤에서 특성 적용"
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
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e4d5bfb445ce6ed37ad1dc63d92fde833ac9870
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="c52ce-102">방법: Windows Forms 컨트롤에서 특성 적용</span><span class="sxs-lookup"><span data-stu-id="c52ce-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="c52ce-103">구성 요소 및 디자인 환경와 제대로 상호 작용 하 고 런타임 시 올바르게 실행 하는 컨트롤을 개발 하려면 클래스와 멤버에 특성을 올바르게 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c52ce-104">예</span><span class="sxs-lookup"><span data-stu-id="c52ce-104">Example</span></span>  
 <span data-ttu-id="c52ce-105">다음 코드 예제에서는 사용자 지정 컨트롤에 여러 특성을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="c52ce-106">컨트롤에는 간단한 로깅 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="c52ce-107">데이터 원본에 의해 전송 되는 값을 표시 컨트롤을 데이터 원본에 바인딩되면는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c52ce-108">값에 지정 된 값을 초과 하는 경우는 `Threshold` 속성에는 `ThresholdExceeded` 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="c52ce-109">`AttributesDemoControl` 값을 기록는 `LogEntry` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="c52ce-110">`LogEntry` 클래스는 템플릿 클래스를 기록 하는 형식 매개 변수가 있다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="c52ce-111">예를 들어 경우는 `AttributesDemoControl` 형식의 로깅 값은 `float`, 각 `LogEntry` 인스턴스를 선언 하 고 다음과 같이 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="c52ce-112">때문에 `LogEntry` 매개 변수화 된 임의의 형식에 의해 매개 변수 형식에서 작동 하도록 리플렉션을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="c52ce-113">임계값 기능을 사용 하 고 매개 변수 형식에 대 한 `T` 구현 해야 합니다는 <xref:System.IComparable> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="c52ce-114">폼을 호스팅하는 `AttributesDemoControl` 정기적으로 성능 카운터를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="c52ce-115">각 값에 패키지 되는 `LogEntry` 적절 한 유형의 폼에 추가 하 고 <xref:System.Windows.Forms.BindingSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="c52ce-116">`AttributesDemoControl` 에 값을 표시 하 고 값을 받습니다. 해당 데이터 바인딩을 통해 한 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="c52ce-117">첫 번째 코드 예제는 `AttributesDemoControl` 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="c52ce-118">두 번째 코드 예제에서는 사용 하는 폼은 `AttributesDemoControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="c52ce-119">클래스 수준 특성</span><span class="sxs-lookup"><span data-stu-id="c52ce-119">Class-level Attributes</span></span>  
 <span data-ttu-id="c52ce-120">일부 특성은 클래스 수준에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="c52ce-121">다음 코드 예제에서는 일반적으로 Windows Forms 컨트롤에 적용 되는 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="c52ce-122">TypeConverter 특성</span><span class="sxs-lookup"><span data-stu-id="c52ce-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="c52ce-123"><xref:System.ComponentModel.TypeConverterAttribute>자주 사용 되는 다른 클래스 수준 특성이입니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="c52ce-124">다음 코드 예제에서는 표시 하는 데 사용 된 `LogEntry` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="c52ce-125">이 예제에는 또한의 구현을 보여 줍니다는 <xref:System.ComponentModel.TypeConverter> 에 대 한는 `LogEntry` 이라는 형식을 `LogEntryTypeConverter`합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="c52ce-126">멤버 수준 특성</span><span class="sxs-lookup"><span data-stu-id="c52ce-126">Member-level Attributes</span></span>  
 <span data-ttu-id="c52ce-127">일부 특성은 멤버 수준에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="c52ce-128">다음 코드 예제는 일반적으로 Windows Forms 컨트롤의 속성에 적용 되는 일부 특성을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="c52ce-129">AmbientValue 특성</span><span class="sxs-lookup"><span data-stu-id="c52ce-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="c52ce-130">다음 예제는 <xref:System.ComponentModel.AmbientValueAttribute> 디자인 환경과 상호 작용을 지 원하는 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="c52ce-131">이러한 상호 작용 라고 *외계*합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="c52ce-132">데이터 바인딩 특성</span><span class="sxs-lookup"><span data-stu-id="c52ce-132">Databinding Attributes</span></span>  
 <span data-ttu-id="c52ce-133">다음 예제에서는 복합 데이터 바인딩의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="c52ce-134">클래스 수준 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>표시 이전에 지정 된 `DataSource` 및 `DataMember` 데이터 바인딩에 사용할 속성을 합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="c52ce-135"><xref:System.ComponentModel.AttributeProviderAttribute> 대상 형식 지정은 `DataSource` 속성 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c52ce-136">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c52ce-136">Compiling the Code</span></span>  
  
-   <span data-ttu-id="c52ce-137">폼을 호스팅하는 `AttributesDemoControl` 에 대 한 참조는 `AttributesDemoControl` 어셈블리를 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c52ce-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c52ce-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c52ce-138">See Also</span></span>  
 <xref:System.IComparable>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="c52ce-139">.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="c52ce-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="c52ce-140">Windows Forms 컨트롤의 특성</span><span class="sxs-lookup"><span data-stu-id="c52ce-140">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 [<span data-ttu-id="c52ce-141">방법: designerserializationvisibilityattribute를 사용 하 여 표준 형식의 컬렉션 Serialize</span><span class="sxs-lookup"><span data-stu-id="c52ce-141">How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)
