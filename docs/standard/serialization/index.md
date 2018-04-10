---
title: .NET의 Serialization
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1a0d9f5fd32b5610e3d7b05455c7bd3c55b5b77e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="serialization-in-net"></a><span data-ttu-id="8beab-102">.NET의 Serialization</span><span class="sxs-lookup"><span data-stu-id="8beab-102">Serialization in .NET</span></span>
<span data-ttu-id="8beab-103">serialization은 지속시키거나 전송할 수 있는 형태로 개체 상태를 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-103">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="8beab-104">serialization과 짝을 이루는 것은 스트림을 개체로 변환하는 deserialization입니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-104">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="8beab-105">이 두 프로세스를 통해 데이터를 쉽게 저장하고 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-105">Together, these processes allow data to be easily stored and transferred.</span></span>  
  
<span data-ttu-id="8beab-106">.NET에서는 다음 두 가지의 serialization 기술을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-106">.NET features two serialization technologies:</span></span>  
  
-   <span data-ttu-id="8beab-107">이진 serialization은 형식 정확도를 유지하므로 응용 프로그램의 여러 호출 간에 개체 상태를 유지하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-107">Binary serialization preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="8beab-108">예를 들어, 개체를 클립보드로 serialize하면 여러 응용 프로그램 간에 개체를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-108">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="8beab-109">개체를 스트림, 디스크, 메모리, 네트워크 등으로 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-109">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="8beab-110">Remoting에서는 serialization을 사용하여 한 컴퓨터 또는 응용 프로그램 도메인의 개체를 다른 컴퓨터 또는 응용 프로그램 도메인으로 "값으로" 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-110">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
-   <span data-ttu-id="8beab-111">XML serialization은 public 속성과 필드만 serialize하며 형식 정확도를 유지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-111">XML serialization serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="8beab-112">데이터를 사용하는 응용 프로그램을 제한하지 않고 데이터를 제공하거나 사용하려고 할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-112">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="8beab-113">XML은 공개 표준이기 때문에 웹을 통해 정보를 공유할 때 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-113">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="8beab-114">SOAP도 마찬가지로 공개 표준이어서 적합한 선택입니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-114">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8beab-115">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="8beab-115">In This Section</span></span>  
[<span data-ttu-id="8beab-116">serialization 방법 항목</span><span class="sxs-lookup"><span data-stu-id="8beab-116">Serialization How-to Topics</span></span>](../../../docs/standard/serialization/serialization-how-to-topics.md)  
<span data-ttu-id="8beab-117">이 단원에 포함된 방법 항목에 대한 링크를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-117">Lists links to How-to topics contained in this section.</span></span>
  
[<span data-ttu-id="8beab-118">이진 serialization</span><span class="sxs-lookup"><span data-stu-id="8beab-118">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)  
<span data-ttu-id="8beab-119">공용 언어 런타임에 포함된 이진 serialization 메커니즘을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-119">Describes the binary serialization mechanism that is included with the common language runtime.</span></span>

[<span data-ttu-id="8beab-120">XML 및 SOAP serialization</span><span class="sxs-lookup"><span data-stu-id="8beab-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
<span data-ttu-id="8beab-121">공용 언어 런타임에 포함된 XML 및 SOAP serialization 메커니즘을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-121">Describes the XML and SOAP serialization mechanism that is included with the common language runtime.</span></span>

[<span data-ttu-id="8beab-122">serialization 도구</span><span class="sxs-lookup"><span data-stu-id="8beab-122">Serialization Tools</span></span>](../../../docs/standard/serialization/serialization-tools.md)  
<span data-ttu-id="8beab-123">이러한 도구는 serialization 코드를 개발하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-123">These tools help develop serialization code.</span></span>

[<span data-ttu-id="8beab-124">serialization 샘플</span><span class="sxs-lookup"><span data-stu-id="8beab-124">Serialization Samples</span></span>](../../../docs/standard/serialization/serialization-samples.md)  
<span data-ttu-id="8beab-125">이러한 샘플에서는 serialization을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-125">The samples demonstrate how to do serialization.</span></span>

## <a name="reference"></a><span data-ttu-id="8beab-126">참조</span><span class="sxs-lookup"><span data-stu-id="8beab-126">Reference</span></span>
<span data-ttu-id="8beab-127"><xref:System.Runtime.Serialization> 개체를 직렬화하거나 deserialize하는 데 사용할 수 있는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-127"><xref:System.Runtime.Serialization> Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="8beab-128">개체를 XML 형식 문서 또는 스트림으로 serialize하는 데 사용할 수 있는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8beab-128">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>