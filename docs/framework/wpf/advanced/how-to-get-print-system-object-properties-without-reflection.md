---
title: "방법: 리플렉션을 사용하지 않고 인쇄 시스템 개체 속성 가져오기"
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
helpviewer_keywords: PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d93919f691b51d5f177b074e5d9cef2c140458e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a><span data-ttu-id="5cebd-102">방법: 리플렉션을 사용하지 않고 인쇄 시스템 개체 속성 가져오기</span><span class="sxs-lookup"><span data-stu-id="5cebd-102">How to: Get Print System Object Properties Without Reflection</span></span>
<span data-ttu-id="5cebd-103">개체에 속성 (및 해당 속성의 형식을)을 항목별로 정리할 리플렉션을 사용 하 여 응용 프로그램 성능이 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cebd-103">Using reflection to itemize the properties (and the types of those properties) on an object can slow application performance.</span></span> <span data-ttu-id="5cebd-104"><xref:System.Printing.IndexedProperties> 네임 스페이스는 리플렉션을 사용 하 여이 정보를 가져올 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cebd-104">The <xref:System.Printing.IndexedProperties> namespace provides a means to getting this information with using reflection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cebd-105">예</span><span class="sxs-lookup"><span data-stu-id="5cebd-105">Example</span></span>  
 <span data-ttu-id="5cebd-106">이 작업을 수행 하는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5cebd-106">The steps for doing this are as follows.</span></span>  
  
1.  <span data-ttu-id="5cebd-107">형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5cebd-107">Create an instance of the type.</span></span> <span data-ttu-id="5cebd-108">형식이 아래 예에서 <xref:System.Printing.PrintQueue> 와 함께 제공 되는 형식 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]에서 파생 되는 형식에 대해 거의 동일한 코드가 작동 해야 하지만 <xref:System.Printing.PrintSystemObject>합니다.</span><span class="sxs-lookup"><span data-stu-id="5cebd-108">In the example below, the type is the <xref:System.Printing.PrintQueue> type that ships with [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], but nearly identical code should work for types that you derive from <xref:System.Printing.PrintSystemObject>.</span></span>  
  
2.  <span data-ttu-id="5cebd-109">만들기는 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> 형식의에서 <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="5cebd-109">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the type's <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span></span> <span data-ttu-id="5cebd-110"><xref:System.Collections.DictionaryEntry.Value%2A> 이 사전에 있는 각 항목의 속성은 개체에서 파생 된 형식 중 하나의 <xref:System.Printing.IndexedProperties.PrintProperty>합니다.</span><span class="sxs-lookup"><span data-stu-id="5cebd-110">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span>  
  
3.  <span data-ttu-id="5cebd-111">사전의 구성원을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cebd-111">Enumerate the members of the dictionary.</span></span> <span data-ttu-id="5cebd-112">각각의 다음 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cebd-112">For each of them, do the following.</span></span>  
  
4.  <span data-ttu-id="5cebd-113">위쪽에 각 항목의 값이 캐스트 <xref:System.Printing.IndexedProperties.PrintProperty> 사용 하 여 만들는 <xref:System.Printing.IndexedProperties.PrintProperty> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5cebd-113">Up-cast the value of each entry to <xref:System.Printing.IndexedProperties.PrintProperty> and use it to create a <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
5.  <span data-ttu-id="5cebd-114">형식을 가져오기는 <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> 각는 <xref:System.Printing.IndexedProperties.PrintProperty> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5cebd-114">Get the type of the <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> of each of the <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a><span data-ttu-id="5cebd-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5cebd-115">See Also</span></span>  
 <xref:System.Printing.IndexedProperties.PrintProperty>  
 <xref:System.Printing.PrintSystemObject>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [<span data-ttu-id="5cebd-116">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="5cebd-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="5cebd-117">인쇄 개요</span><span class="sxs-lookup"><span data-stu-id="5cebd-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
