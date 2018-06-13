---
title: '방법: 프린터 복제'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
ms.openlocfilehash: 8f3a9c3b4d9f4bcbe3a6ffcff9868aa7b19b8f28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544205"
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="f25f2-102">방법: 프린터 복제</span><span class="sxs-lookup"><span data-stu-id="f25f2-102">How to: Clone a Printer</span></span>
<span data-ttu-id="f25f2-103">대부분의 기업, 어느 시점 부터는 구입할지 동일한 모델의 여러 프린터입니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="f25f2-104">일반적으로 모든 설치 실제로 동일한 구성 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="f25f2-105">각 프린터를 설치 시간이 오래 걸릴 수 및 오류가 발생 하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="f25f2-106"><xref:System.Printing.IndexedProperties?displayProperty=nameWithType> 네임 스페이스 및 <xref:System.Printing.PrintServer.InstallPrintQueue%2A> Microsoft.NET Framework로 노출 되는 클래스를 사용 하면 즉시 추가 인쇄 큐는 복제를 개수에 관계 없이 기존 인쇄 대기열에서 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with Microsoft .NET Framework makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f25f2-107">예제</span><span class="sxs-lookup"><span data-stu-id="f25f2-107">Example</span></span>  
 <span data-ttu-id="f25f2-108">아래 예제에서는 두 번째 인쇄 큐는 기존 인쇄 대기열에서 복제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="f25f2-109">두 번째 다른 첫 번째에서 이름, 위치, 포트 및 공유 상태에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="f25f2-110">이 작업을 위한 주요 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-110">The major steps for doing this are as follows.</span></span>  
  
1.  <span data-ttu-id="f25f2-111">만들기는 <xref:System.Printing.PrintQueue> 기존 프린터에 복제에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2.  <span data-ttu-id="f25f2-112">만들기는 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> 에서 <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> 의 <xref:System.Printing.PrintQueue>합니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="f25f2-113"><xref:System.Collections.DictionaryEntry.Value%2A> 이 사전에 있는 각 항목의 속성은 개체에서 파생 된 형식 중 하나의 <xref:System.Printing.IndexedProperties.PrintProperty>합니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="f25f2-114">이 사전에 있는 항목의 값을 설정 하는 방법은 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    -   <span data-ttu-id="f25f2-115">사전을 사용 하 여 **제거** 및 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> 메서드 하는 항목을 제거 하 고 원하는 값으로 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    -   <span data-ttu-id="f25f2-116">사전을 사용 하 여 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="f25f2-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="f25f2-117">다음 예제에서는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-117">The example below illustrates both ways.</span></span>  
  
3.  <span data-ttu-id="f25f2-118">만들기는 <xref:System.Printing.IndexedProperties.PrintBooleanProperty> 개체 및 설정의 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "IsShared"를 및 해당 <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> 를 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4.  <span data-ttu-id="f25f2-119">사용 하 여는 <xref:System.Printing.IndexedProperties.PrintBooleanProperty> 개체의 값 수는 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>의 "IsShared" 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5.  <span data-ttu-id="f25f2-120">만들기는 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체 및 설정 해당 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> 을 "ShareName" 및 해당 <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> 를 적절 한 <xref:System.String>합니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6.  <span data-ttu-id="f25f2-121">사용 하 여는 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체의 값 수는 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>의 "ShareName" 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7.  <span data-ttu-id="f25f2-122">다른 만들 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체 및 설정의 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "위치" 및 해당 <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> 를 적절 한 <xref:System.String>합니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8.  <span data-ttu-id="f25f2-123">두 번째 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체의 값 수는 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>의 "위치" 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="f25f2-124">배열을 만들어 <xref:System.String>s입니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="f25f2-125">각 항목에는 서버에서 포트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="f25f2-126">사용 하 여 <xref:System.Printing.PrintServer.InstallPrintQueue%2A> 새 값으로 새 프린터를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="f25f2-127">아래 예가입니다.</span><span class="sxs-lookup"><span data-stu-id="f25f2-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="f25f2-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f25f2-128">See Also</span></span>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [<span data-ttu-id="f25f2-129">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="f25f2-129">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="f25f2-130">인쇄 개요</span><span class="sxs-lookup"><span data-stu-id="f25f2-130">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
