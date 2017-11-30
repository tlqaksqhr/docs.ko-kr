---
title: "WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
api_name: System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location: System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be93ddc0f3bf0a5079f31bfa0ff5caa882342c37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a><span data-ttu-id="bfbfd-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) 메서드</span><span class="sxs-lookup"><span data-stu-id="bfbfd-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Method</span></span>
<span data-ttu-id="bfbfd-103">[.NET Framework 4.5.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="bfbfd-103">[Supported in the .NET Framework 4.5.1 and later versions]</span></span>  
  
 <span data-ttu-id="bfbfd-104">지정된 스트림을 임의 액세스 스트림으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbfd-104">Converts the specified stream to a random access stream.</span></span>  
  
 <span data-ttu-id="bfbfd-105">**Namespace:**<xref:System.IO?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bfbfd-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType></span></span>  
 <span data-ttu-id="bfbfd-106">**어셈블리:** System.Runtime.WindowsRuntime (system.runtime.windowsruntime.dll에서)</span><span class="sxs-lookup"><span data-stu-id="bfbfd-106">**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfbfd-107">구문</span><span class="sxs-lookup"><span data-stu-id="bfbfd-107">Syntax</span></span>  
  
```csharp  
[CLSCompliantAttribute(false)]  
public static  IRandomAccessStream AsRandomAccessStream(Stream stream)  
```  
  
```vb  
'Declaration  
<ExtensionAttribute> _  
<CLSCompliantAttribute(False)> _  
Public Shared Function AsRandomAccessStream ( _  
        stream As Stream) As IRandomAccessStream  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bfbfd-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bfbfd-108">Parameters</span></span>  
 `stream`  
  
 <span data-ttu-id="bfbfd-109">형식: <xref:System.IO.Stream?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bfbfd-109">Type: <xref:System.IO.Stream?displayProperty=nameWithType></span></span>  
<span data-ttu-id="bfbfd-110">변환할 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="bfbfd-110">The stream to convert.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfbfd-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="bfbfd-111">Return Value</span></span>  
 <span data-ttu-id="bfbfd-112">형식: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span><span class="sxs-lookup"><span data-stu-id="bfbfd-112">Type: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span></span>  
<span data-ttu-id="bfbfd-113">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] 임의 액세스 스트림은 변환된 된 스트림을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bfbfd-113">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] random access stream, which represents the converted stream.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="bfbfd-114">예외</span><span class="sxs-lookup"><span data-stu-id="bfbfd-114">Exceptions</span></span>  
  
|<span data-ttu-id="bfbfd-115">예외</span><span class="sxs-lookup"><span data-stu-id="bfbfd-115">Exception</span></span>|<span data-ttu-id="bfbfd-116">조건</span><span class="sxs-lookup"><span data-stu-id="bfbfd-116">Condition</span></span>|  
|---------------|---------------|  
|<xref:System.NotSupportedException>|<span data-ttu-id="bfbfd-117">변환할 스트림은 검색을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbfd-117">The stream to convert does not support seeking.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfbfd-118">설명</span><span class="sxs-lookup"><span data-stu-id="bfbfd-118">Remarks</span></span>  
 <span data-ttu-id="bfbfd-119">이 확장 메서드는 Windows 스토어 앱을 개발하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbfd-119">This extension method is available only when you develop Windows Store apps.</span></span> <span data-ttu-id="bfbfd-120">이 메서드는 Windows 스토어 앱의 스트림을 작업하는 데 편리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbfd-120">This method provides a convenient way of working with streams in Windows Store apps.</span></span> <span data-ttu-id="bfbfd-121">변환하려는 .NET Framework 스트림은 검색을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbfd-121">The .NET Framework stream you want to convert must support seeking.</span></span> <span data-ttu-id="bfbfd-122">자세한 내용은 <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> 메서드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bfbfd-122">For more information, see the <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bfbfd-123">이 API는 .NET Framework 4.5.1 이상 버전에서 지원되지만 4.5 버전에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbfd-123">This API is supported in the .NET Framework 4.5.1 and later versions, but not in version 4.5.</span></span>  
  
## <a name="version-information"></a><span data-ttu-id="bfbfd-124">버전 정보</span><span class="sxs-lookup"><span data-stu-id="bfbfd-124">Version Information</span></span>  
 <span data-ttu-id="bfbfd-125">**Windows 스토어 앱 용.NET**</span><span class="sxs-lookup"><span data-stu-id="bfbfd-125">**.NET for Windows Store apps**</span></span>  
  
 <span data-ttu-id="bfbfd-126">지원: Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="bfbfd-126">Supported in: Windows 8.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfbfd-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfbfd-127">See Also</span></span>  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions`  
 [<span data-ttu-id="bfbfd-128">방법: .NET Framework 스트림과 Windows 런타임 스트림 간 변환</span><span class="sxs-lookup"><span data-stu-id="bfbfd-128">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
