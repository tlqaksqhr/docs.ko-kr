---
title: WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) 메서드
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
api_name:
- System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location:
- System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16f878abc11589fe62f78d941b367d82d7b49e1c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32768517"
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a><span data-ttu-id="07dc5-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) 메서드</span><span class="sxs-lookup"><span data-stu-id="07dc5-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Method</span></span>
<span data-ttu-id="07dc5-103">[.NET Framework 4.5.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="07dc5-103">[Supported in the .NET Framework 4.5.1 and later versions]</span></span>  
  
 <span data-ttu-id="07dc5-104">지정된 스트림을 임의 액세스 스트림으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="07dc5-104">Converts the specified stream to a random access stream.</span></span>  
  
 <span data-ttu-id="07dc5-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="07dc5-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType></span></span>  
 <span data-ttu-id="07dc5-106">**어셈블리:** System.Runtime.WindowsRuntime (system.runtime.windowsruntime.dll에서)</span><span class="sxs-lookup"><span data-stu-id="07dc5-106">**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07dc5-107">구문</span><span class="sxs-lookup"><span data-stu-id="07dc5-107">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="07dc5-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="07dc5-108">Parameters</span></span>  
 `stream`  
  
 <span data-ttu-id="07dc5-109">형식: <xref:System.IO.Stream?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="07dc5-109">Type: <xref:System.IO.Stream?displayProperty=nameWithType></span></span>  
<span data-ttu-id="07dc5-110">변환할 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="07dc5-110">The stream to convert.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07dc5-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="07dc5-111">Return Value</span></span>  
 <span data-ttu-id="07dc5-112">형식: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span><span class="sxs-lookup"><span data-stu-id="07dc5-112">Type: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span></span>  
<span data-ttu-id="07dc5-113">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] 임의 액세스 스트림은 변환된 된 스트림을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="07dc5-113">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] random access stream, which represents the converted stream.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="07dc5-114">예외</span><span class="sxs-lookup"><span data-stu-id="07dc5-114">Exceptions</span></span>  
  
|<span data-ttu-id="07dc5-115">예외</span><span class="sxs-lookup"><span data-stu-id="07dc5-115">Exception</span></span>|<span data-ttu-id="07dc5-116">조건</span><span class="sxs-lookup"><span data-stu-id="07dc5-116">Condition</span></span>|  
|---------------|---------------|  
|<xref:System.NotSupportedException>|<span data-ttu-id="07dc5-117">변환할 스트림은 검색을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07dc5-117">The stream to convert does not support seeking.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07dc5-118">설명</span><span class="sxs-lookup"><span data-stu-id="07dc5-118">Remarks</span></span>  
 <span data-ttu-id="07dc5-119">이 확장 메서드는 Windows 스토어 앱을 개발하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dc5-119">This extension method is available only when you develop Windows Store apps.</span></span> <span data-ttu-id="07dc5-120">이 메서드는 Windows 스토어 앱의 스트림을 작업하는 데 편리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07dc5-120">This method provides a convenient way of working with streams in Windows Store apps.</span></span> <span data-ttu-id="07dc5-121">변환하려는 .NET Framework 스트림은 검색을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07dc5-121">The .NET Framework stream you want to convert must support seeking.</span></span> <span data-ttu-id="07dc5-122">자세한 내용은 <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> 메서드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07dc5-122">For more information, see the <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="07dc5-123">이 API는 .NET Framework 4.5.1 이상 버전에서 지원되지만 4.5 버전에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07dc5-123">This API is supported in the .NET Framework 4.5.1 and later versions, but not in version 4.5.</span></span>  
  
## <a name="version-information"></a><span data-ttu-id="07dc5-124">버전 정보</span><span class="sxs-lookup"><span data-stu-id="07dc5-124">Version Information</span></span>  
 <span data-ttu-id="07dc5-125">**Windows 스토어 앱 용.NET**</span><span class="sxs-lookup"><span data-stu-id="07dc5-125">**.NET for Windows Store apps**</span></span>  
  
 <span data-ttu-id="07dc5-126">지원: Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="07dc5-126">Supported in: Windows 8.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07dc5-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07dc5-127">See Also</span></span>  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions`  
 [<span data-ttu-id="07dc5-128">방법: .NET Framework 스트림과 Windows 런타임 스트림 간 변환</span><span class="sxs-lookup"><span data-stu-id="07dc5-128">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
