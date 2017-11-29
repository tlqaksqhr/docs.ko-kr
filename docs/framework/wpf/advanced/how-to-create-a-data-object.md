---
title: "방법: 데이터 개체 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7b002e1c7a9eea2592de58aac3b838b9f6f982ce
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="c6d47-102">방법: 데이터 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="c6d47-102">How to: Create a Data Object</span></span>
<span data-ttu-id="c6d47-103">다음 예제에서 제공 하는 생성자를 사용 하 여 데이터 개체를 만드는 다양 한 방법을 보여 줍니다는 <xref:System.Windows.DataObject> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d47-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6d47-104">예제</span><span class="sxs-lookup"><span data-stu-id="c6d47-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c6d47-105">설명</span><span class="sxs-lookup"><span data-stu-id="c6d47-105">Description</span></span>  
 <span data-ttu-id="c6d47-106">다음 코드 예제에서는 새 데이터 개체를 만들고 오버 로드 된 생성자 중 하나를 사용 하 여 (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) 문자열이 있는 데이터 개체를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d47-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="c6d47-107">이 경우 해당 데이터 형식이 자동으로 저장된 된 데이터 형식에 따라 결정 됩니다 하 고 저장된 된 데이터 자동 변환 기본적으로 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6d47-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c6d47-108">코드</span><span class="sxs-lookup"><span data-stu-id="c6d47-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="c6d47-109">설명</span><span class="sxs-lookup"><span data-stu-id="c6d47-109">Description</span></span>  
 <span data-ttu-id="c6d47-110">다음 예제 코드는 위에 나와 있는 코드의 압축 된 버전.</span><span class="sxs-lookup"><span data-stu-id="c6d47-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c6d47-111">코드</span><span class="sxs-lookup"><span data-stu-id="c6d47-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="c6d47-112">예제</span><span class="sxs-lookup"><span data-stu-id="c6d47-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c6d47-113">설명</span><span class="sxs-lookup"><span data-stu-id="c6d47-113">Description</span></span>  
 <span data-ttu-id="c6d47-114">다음 코드 예제에서는 새 데이터 개체를 만들고 오버 로드 된 생성자 중 하나를 사용 하 여 (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) 문자열 및 지정 된 데이터 형식으로 데이터 개체를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d47-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="c6d47-115">데이터 형식은 문자열;에 의해 지정은 경우 <xref:System.Windows.DataFormats> 클래스 미리 정의 된 형식 문자열의 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d47-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="c6d47-116">기본적으로 저장된 된 데이터 자동 변환 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6d47-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c6d47-117">코드</span><span class="sxs-lookup"><span data-stu-id="c6d47-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="c6d47-118">설명</span><span class="sxs-lookup"><span data-stu-id="c6d47-118">Description</span></span>  
 <span data-ttu-id="c6d47-119">다음 예제 코드는 위에 나와 있는 코드의 압축 된 버전.</span><span class="sxs-lookup"><span data-stu-id="c6d47-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c6d47-120">코드</span><span class="sxs-lookup"><span data-stu-id="c6d47-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="c6d47-121">예제</span><span class="sxs-lookup"><span data-stu-id="c6d47-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c6d47-122">설명</span><span class="sxs-lookup"><span data-stu-id="c6d47-122">Description</span></span>  
 <span data-ttu-id="c6d47-123">다음 코드 예제에서는 새 데이터 개체를 만들고 오버 로드 된 생성자 중 하나를 사용 하 여 (<xref:System.Windows.DataObject.%23ctor%2A>) 문자열 및 지정 된 데이터 형식으로 데이터 개체를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d47-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="c6d47-124">데이터 format을 지정 하는 경우에 <xref:System.Type> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d47-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="c6d47-125">기본적으로 저장된 된 데이터 자동 변환 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6d47-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c6d47-126">코드</span><span class="sxs-lookup"><span data-stu-id="c6d47-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="c6d47-127">설명</span><span class="sxs-lookup"><span data-stu-id="c6d47-127">Description</span></span>  
 <span data-ttu-id="c6d47-128">다음 예제 코드는 위에 나와 있는 코드의 압축 된 버전.</span><span class="sxs-lookup"><span data-stu-id="c6d47-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c6d47-129">코드</span><span class="sxs-lookup"><span data-stu-id="c6d47-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="c6d47-130">예제</span><span class="sxs-lookup"><span data-stu-id="c6d47-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c6d47-131">설명</span><span class="sxs-lookup"><span data-stu-id="c6d47-131">Description</span></span>  
 <span data-ttu-id="c6d47-132">다음 코드 예제에서는 새 데이터 개체를 만들고 오버 로드 된 생성자 중 하나를 사용 하 여 (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) 문자열 및 지정 된 데이터 형식으로 데이터 개체를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d47-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="c6d47-133">데이터 형식은 문자열;에 의해 지정은 경우 <xref:System.Windows.DataFormats> 클래스 미리 정의 된 형식 문자열의 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d47-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="c6d47-134">이 특정 생성자 오버 로드에는 자동 변환 허용 되는지 여부를 지정 하려면 호출자 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6d47-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c6d47-135">코드</span><span class="sxs-lookup"><span data-stu-id="c6d47-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="c6d47-136">설명</span><span class="sxs-lookup"><span data-stu-id="c6d47-136">Description</span></span>  
 <span data-ttu-id="c6d47-137">다음 예제 코드는 위에 나와 있는 코드의 압축 된 버전.</span><span class="sxs-lookup"><span data-stu-id="c6d47-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c6d47-138">코드</span><span class="sxs-lookup"><span data-stu-id="c6d47-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="c6d47-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6d47-139">See Also</span></span>  
 <xref:System.Windows.IDataObject>
