---
title: "BindingSource 구성 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 006cafafdf8e3c3f4da77394d6155fa52e113b58
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="bindingsource-component"></a><span data-ttu-id="c4127-102">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c4127-102">BindingSource Component</span></span>
<span data-ttu-id="c4127-103">컨트롤에 바인딩할 데이터 소스를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-103">Encapsulates a data source for binding to controls.</span></span>  
  
 <span data-ttu-id="c4127-104"><xref:System.Windows.Forms.BindingSource> 구성 요소는 두가지 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-104">The <xref:System.Windows.Forms.BindingSource> component serves two purposes.</span></span> <span data-ttu-id="c4127-105">첫째, 폼의 컨트롤을 데이터에 바인딩할 때 간접 참조 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-105">First, it provides a layer of indirection when binding the controls on a form to data.</span></span> <span data-ttu-id="c4127-106">이 작업은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 데이터 소스에 바인딩한 다음 폼의 컨트롤을 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-106">This is accomplished by binding the <xref:System.Windows.Forms.BindingSource> component to your data source, and then binding the controls on your form to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="c4127-107">탐색, 정렬, 필터링, 업데이트 등 데이터와의 모든 상호 작용은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 호출하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-107">All further interaction with the data, including navigating, sorting, filtering, and updating, is accomplished with calls to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="c4127-108">둘째, <xref:System.Windows.Forms.BindingSource> 구성 요소는 강력한 형식의 데이터 소스로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-108">Second, the <xref:System.Windows.Forms.BindingSource> component can act as a strongly typed data source.</span></span> <span data-ttu-id="c4127-109"><xref:System.Windows.Forms.BindingSource.Add%2A> 메서드를 통해 <xref:System.Windows.Forms.BindingSource> 구성 요소에 형식을 추가하면 해당 형식의 목록이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-109">Adding a type to the <xref:System.Windows.Forms.BindingSource> component with the <xref:System.Windows.Forms.BindingSource.Add%2A> method creates a list of that type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4127-110">단원 내용</span><span class="sxs-lookup"><span data-stu-id="c4127-110">In This Section</span></span>  
 [<span data-ttu-id="c4127-111">BindingSource 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="c4127-111">BindingSource Component Overview</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)  
 <span data-ttu-id="c4127-112">데이터 소스를 컨트롤에 바인딩할 수 있게 해주는 <xref:System.Windows.Forms.BindingSource> 구성 요소의 일반적인 개념을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-112">Introduces the general concepts of the <xref:System.Windows.Forms.BindingSource> component, which allows you to bind a data source to a control.</span></span>  
  
 [<span data-ttu-id="c4127-113">방법: DBNull 데이터베이스 값에 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="c4127-113">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 <span data-ttu-id="c4127-114"><xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 데이터 소스의 <xref:System.DBNull> 값을 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-114">Shows how to handle a <xref:System.DBNull> value from the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="c4127-115">방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링</span><span class="sxs-lookup"><span data-stu-id="c4127-115">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 <span data-ttu-id="c4127-116"><xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 표시된 데이터에 정렬 및 필터를 적용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-116">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to apply sorts and filters to displayed data.</span></span>  
  
 [<span data-ttu-id="c4127-117">방법: Windows Forms BindingSource를 사용하여 웹 서비스에 바인딩</span><span class="sxs-lookup"><span data-stu-id="c4127-117">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="c4127-118"><xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 웹 서비스에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-118">Shows how to use the <xref:System.Windows.Forms.BindingSource> component to bind to a Web service.</span></span>  
  
 [<span data-ttu-id="c4127-119">방법: 데이터 바인딩에서 발생하는 오류 및 예외 처리</span><span class="sxs-lookup"><span data-stu-id="c4127-119">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 <span data-ttu-id="c4127-120"><xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 데이터 바인딩 작업에서 발생하는 오류를 정상적으로 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-120">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to gracefully handle errors that occur in a data binding operation.</span></span>  
  
 [<span data-ttu-id="c4127-121">방법: 형식에 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="c4127-121">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 <span data-ttu-id="c4127-122"><xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 형식에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-122">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a type.</span></span>  
  
 [<span data-ttu-id="c4127-123">방법: 팩터리 개체에 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="c4127-123">How to: Bind a Windows Forms Control to a Factory Object</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 <span data-ttu-id="c4127-124"><xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 팩터리 개체나 메서드에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-124">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a factory object or method.</span></span>  
  
 [<span data-ttu-id="c4127-125">방법: Windows Forms BindingSource를 사용하여 항목 추가 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="c4127-125">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="c4127-126"><xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 새 항목을 만들고 데이터 소스에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-126">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to create new items and add them to a data source.</span></span>  
  
 [<span data-ttu-id="c4127-127">방법: BindingSource ResetItem 메서드를 사용하여 변경 알림 발생</span><span class="sxs-lookup"><span data-stu-id="c4127-127">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](../../../../docs/framework/winforms/controls/how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 <span data-ttu-id="c4127-128"><xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 변경 알림을 지원하지 않는 데이터 소스에 대한 변경 알림 이벤트를 발생시키는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-128">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to raise change-notification events for data sources that do not support change notification.</span></span>  
  
 [<span data-ttu-id="c4127-129">방법: BindingSource와 INotifyPropertyChanged 인터페이스를 사용하여 변경 내용 알림 발생</span><span class="sxs-lookup"><span data-stu-id="c4127-129">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](../../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)  
 <span data-ttu-id="c4127-130"><xref:System.Windows.Forms.BindingSource> 컨트롤을 통해 <xref:System.ComponentModel.INotifyPropertyChanged>에서 상속되는 형식을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-130">Demonstrates how to use a type that inherits from the <xref:System.ComponentModel.INotifyPropertyChanged> with a <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
 [<span data-ttu-id="c4127-131">방법: BindingSource가 있는 Windows Forms 컨트롤에 데이터 소스 업데이트 내용 반영</span><span class="sxs-lookup"><span data-stu-id="c4127-131">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 <span data-ttu-id="c4127-132"><xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 데이터 소스의 변경 내용에 응답하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-132">Demonstrates how to respond to changes in the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="c4127-133">방법: BindingSource 구성 요소를 사용하여 양식 간에 바인딩된 데이터 공유</span><span class="sxs-lookup"><span data-stu-id="c4127-133">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 <span data-ttu-id="c4127-134"><xref:System.Windows.Forms.BindingSource>를 사용하여 여러 개의 폼을 동일한 데이터 소스에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-134">Shows how to use the <xref:System.Windows.Forms.BindingSource> to bind multiple forms to the same data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c4127-135">참조</span><span class="sxs-lookup"><span data-stu-id="c4127-135">Reference</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="c4127-136"><xref:System.Windows.Forms.BindingSource> 구성 요소에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-136">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 <span data-ttu-id="c4127-137"><xref:System.Windows.Forms.BindingNavigator> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c4127-138">관련 단원</span><span class="sxs-lookup"><span data-stu-id="c4127-138">Related Sections</span></span>  
 [<span data-ttu-id="c4127-139">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="c4127-139">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 <span data-ttu-id="c4127-140">Windows Forms 데이터 바인딩 아키텍처를 설명하는 항목의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c4127-140">Contains links to topics describing the Windows Forms data binding architecture.</span></span>  
  
 <span data-ttu-id="c4127-141">[Visual Studio에서 데이터에 컨트롤 바인딩](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)도 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4127-141">Also see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>
