---
title: "이진 Serialization"
ms.date: 08/11/2017
ms.prod: .net
ms.topic: article
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
caps.latest.revision: "5"
author: ViktorHofer
ms.author: mairaw
ms.openlocfilehash: 74ee4e21934c1e4f3fd008664b1315429dc47b37
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="binary-serialization"></a><span data-ttu-id="0edba-102">이진 Serialization</span><span class="sxs-lookup"><span data-stu-id="0edba-102">Binary serialization</span></span>

<span data-ttu-id="0edba-103">serialization은 개체의 상태를 저장 매체에 저장하는 프로세스로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-103">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="0edba-104">이 프로세스 도중 클래스가 포함된 어셈블리를 포함하여 개체의 public 및 private 필드와 클래스의 이름을 바이트의 스트림으로 변환한 다음 데이터 스트림에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-104">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="0edba-105">그런 다음 개체가 deserialize되면 원본 개체의 정확한 복제본이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-105">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="0edba-106">개체 지향적 환경에서 serialization 메커니즘을 구현할 때는 사용 편의성과 유연성 사이에서 균형을 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-106">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="0edba-107">프로세스를 충분히 제어할 수 있으면 프로세스의 많은 부분을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-107">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="0edba-108">예를 들어 단순한 이진 serialization로 충분하지 않거나 클래스의 필드를 serialize해야 하는 것으로 결정할 특별한 이유가 있는 상황이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-108">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="0edba-109">다음 섹션에서는 .NET에서 제공하는 강력한 serialization 메커니즘을 살펴보고 프로세스를 필요에 따라 사용자 지정할 수 있는 몇 가지 중요한 기능을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-109">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="0edba-110">UTF-8 또는 UTF-7로 인코딩된 개체가 서로 다른 .NET Framework 버전을 사용하여 serialize되고 deserialize될 경우 해당 개체의 상태는 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-110">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="0edba-111">이진 serialization은 기본적으로 개체 내에서 전용 멤버의 수정과 상태 변경을 허용하므로 공용 API 화면에서 작동하는 JSON.NET 등의 다른 serialization 프레임워크를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-111">As the nature of binary serialization allows the modification of private members inside an object and therefore changing the state of it, other serialization frameworks like JSON.NET which operate on the public API surface are recommended.</span></span>

## <a name="binary-serialization-in-net-core"></a><span data-ttu-id="0edba-112">.NET Core의 이진 serialization</span><span class="sxs-lookup"><span data-stu-id="0edba-112">Binary serialization in .NET Core</span></span>

<span data-ttu-id="0edba-113">.NET Core는 형식의 하위 집합에서 이진 serialization을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-113">.NET Core supports binary serialization with a subset of types.</span></span> <span data-ttu-id="0edba-114">지원되는 형식 목록은 [직렬화 가능 형식 섹션](#serializable-types)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-114">You can see the list of supported types in the [Serializable types section](#serializable-types).</span></span> <span data-ttu-id="0edba-115">정의된 형식 집합은 .NET Framework 4.5.1 이상 버전 및 .NET Core 2.0 이상 버전 간에 직렬화 가능 형식으로 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-115">The defined set of types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="0edba-116">Mono 등의 다른 .NET 구현은 공식적으로 지원되지 않지만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-116">Other .NET implementations, such as Mono, aren't officially supported but should also be working.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="0edba-117">직렬화 가능 형식</span><span class="sxs-lookup"><span data-stu-id="0edba-117">Serializable types</span></span>

- <xref:System.AggregateException?displayProperty=nameWithType>   
- <xref:System.Array?displayProperty=nameWithType>   
- <xref:System.ArraySegment%601?displayProperty=nameWithType>   
- <xref:System.Attribute?displayProperty=nameWithType>   
- <xref:System.Boolean?displayProperty=nameWithType>   
- <xref:System.Byte?displayProperty=nameWithType>   
- <xref:System.Char?displayProperty=nameWithType>   
- <xref:System.Collections.ArrayList?displayProperty=nameWithType>   
- <xref:System.Collections.BitArray?displayProperty=nameWithType>   
- <xref:System.Collections.Comparer?displayProperty=nameWithType>   
- <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType>   
- <xref:System.Collections.Hashtable?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>   
- <xref:System.Collections.Queue?displayProperty=nameWithType>   
- <xref:System.Collections.SortedList?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType>   
- <xref:System.Collections.Stack?displayProperty=nameWithType>   
- <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType>   
- <span data-ttu-id="0edba-118"><xref:System.DBNull?displayProperty=nameWithType>(.NET Core 2.0.2 이상 버전에서 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="0edba-118"><xref:System.DBNull?displayProperty=nameWithType> (available in .NET Core 2.0.2 and later versions)</span></span>   
- <xref:System.Data.DataSet?displayProperty=nameWithType>   
- <xref:System.Data.DataTable?displayProperty=nameWithType>   
- <xref:System.Data.PropertyCollection?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType>   
- <xref:System.DateTime?displayProperty=nameWithType>   
- <xref:System.DateTimeOffset?displayProperty=nameWithType>   
- <xref:System.Decimal?displayProperty=nameWithType>   
- <xref:System.Double?displayProperty=nameWithType>   
- <xref:System.Drawing.Color?displayProperty=nameWithType>   
- <xref:System.Drawing.Point?displayProperty=nameWithType>   
- <xref:System.Drawing.PointF?displayProperty=nameWithType>   
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>   
- <xref:System.Drawing.RectangleF?displayProperty=nameWithType>   
- <xref:System.Drawing.Size?displayProperty=nameWithType>   
- <xref:System.Drawing.SizeF?displayProperty=nameWithType>   
- <xref:System.Enum?displayProperty=nameWithType>   
- <xref:System.Exception?displayProperty=nameWithType>   
- <xref:System.Globalization.CompareInfo?displayProperty=nameWithType>   
- <xref:System.Globalization.SortVersion?displayProperty=nameWithType>   
- <xref:System.Guid?displayProperty=nameWithType>   
- <xref:System.Int16?displayProperty=nameWithType>   
- <xref:System.Int32?displayProperty=nameWithType>   
- <xref:System.Int64?displayProperty=nameWithType>   
- <xref:System.IntPtr?displayProperty=nameWithType>   
- <xref:System.Net.Cookie?displayProperty=nameWithType>   
- <xref:System.Net.CookieCollection?displayProperty=nameWithType>   
- <xref:System.Net.CookieContainer?displayProperty=nameWithType>   
- <xref:System.Nullable%601?displayProperty=nameWithType>   
- <xref:System.Numerics.BigInteger?displayProperty=nameWithType>   
- <xref:System.Numerics.Complex?displayProperty=nameWithType>   
- <xref:System.Object?displayProperty=nameWithType>   
- <xref:System.SByte?displayProperty=nameWithType>   
- <xref:System.Single?displayProperty=nameWithType>   
- <xref:System.String?displayProperty=nameWithType>   
- <xref:System.StringComparer?displayProperty=nameWithType>   
- <xref:System.Text.StringBuilder?displayProperty=nameWithType>   
- <xref:System.TimeSpan?displayProperty=nameWithType>   
- <xref:System.TimeZoneInfo?displayProperty=nameWithType>   
- <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType>   
- <xref:System.Tuple?displayProperty=nameWithType>   
- <xref:System.UInt16?displayProperty=nameWithType>   
- <xref:System.UInt32?displayProperty=nameWithType>   
- <xref:System.UInt64?displayProperty=nameWithType>   
- <xref:System.UIntPtr?displayProperty=nameWithType>   
- <xref:System.Uri?displayProperty=nameWithType>   
- <span data-ttu-id="0edba-119"><xref:System.ValueTuple?displayProperty=nameWithType>(.NET Framework 4.7 및 이전 버전에서 직렬화 가능 하지)</span><span class="sxs-lookup"><span data-stu-id="0edba-119"><xref:System.ValueTuple?displayProperty=nameWithType> (not serializable in .NET Framework 4.7 and earlier versions)</span></span>  
- <xref:System.ValueType?displayProperty=nameWithType>   
- <xref:System.Version?displayProperty=nameWithType>   
- <xref:System.WeakReference?displayProperty=nameWithType>   
- <xref:System.WeakReference%601?displayProperty=nameWithType>   

## <a name="in-this-section"></a><span data-ttu-id="0edba-120">단원 내용</span><span class="sxs-lookup"><span data-stu-id="0edba-120">In this section</span></span>

 [<span data-ttu-id="0edba-121">serialization 개념</span><span class="sxs-lookup"><span data-stu-id="0edba-121">Serialization Concepts</span></span>](../../../docs/standard/serialization/serialization-concepts.md)  
 <span data-ttu-id="0edba-122">serialization이 유용하게 사용되는 두 가지 경우, 즉 저장소에 데이터를 유지할 경우와 응용 프로그램 도메인에 개체를 전달할 경우에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-122">Discusses two scenarios where serialization is useful: when persisting data to storage and when passing objects across application domains.</span></span>  
  
 [<span data-ttu-id="0edba-123">기본 serialization</span><span class="sxs-lookup"><span data-stu-id="0edba-123">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)  
 <span data-ttu-id="0edba-124">이진 및 SOAP 포맷터를 사용하여 개체를 serialize하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-124">Describes how to use the binary and SOAP formatters to serialize objects.</span></span>  
  
 [<span data-ttu-id="0edba-125">선택적 serialization</span><span class="sxs-lookup"><span data-stu-id="0edba-125">Selective Serialization</span></span>](../../../docs/standard/serialization/selective-serialization.md)  
 <span data-ttu-id="0edba-126">클래스의 일부 멤버가 serialize되는 것을 방지하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-126">Describes how to prevent some members of a class from being serialized.</span></span>  
  
 [<span data-ttu-id="0edba-127">사용자 지정 serialization</span><span class="sxs-lookup"><span data-stu-id="0edba-127">Custom Serialization</span></span>](../../../docs/standard/serialization/custom-serialization.md)  
 <span data-ttu-id="0edba-128"><xref:System.Runtime.Serialization.ISerializable> 인터페이스를 사용하여 클래스에 대한 serialization을 사용자 지정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-128">Describes how to customize serialization for a class by using the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>  
  
 [<span data-ttu-id="0edba-129">serialization 프로세스의 단계</span><span class="sxs-lookup"><span data-stu-id="0edba-129">Steps in the Serialization Process</span></span>](../../../docs/standard/serialization/steps-in-the-serialization-process.md)  
 <span data-ttu-id="0edba-130">포맷터에서 <xref:System.Runtime.Serialization.Formatter.Serialize%2A> 메서드가 호출될 때 serialization이 수행하는 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-130">Describes the course of action serialization takes when the <xref:System.Runtime.Serialization.Formatter.Serialize%2A> method is called on a formatter.</span></span>  
  
 [<span data-ttu-id="0edba-131">버전 독립적 serialization</span><span class="sxs-lookup"><span data-stu-id="0edba-131">Version Tolerant Serialization</span></span>](../../../docs/standard/serialization/version-tolerant-serialization.md)  
 <span data-ttu-id="0edba-132">응용 프로그램에서 예외가 throw되는 것을 방지하면서 시간 경과에 따라 수정할 수 있는 serialize 가능 형식을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-132">Explains how to create serializable types that can be modified over time without causing applications to throw exceptions.</span></span>  
  
 [<span data-ttu-id="0edba-133">serialization 지침</span><span class="sxs-lookup"><span data-stu-id="0edba-133">Serialization Guidelines</span></span>](../../../docs/standard/serialization/serialization-guidelines.md)  
 <span data-ttu-id="0edba-134">개체를 serialize하는 시점을 결정하기 위한 일반 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-134">Provides some general guidelines for deciding when to serialize an object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0edba-135">참조</span><span class="sxs-lookup"><span data-stu-id="0edba-135">Reference</span></span>  
 <xref:System.Runtime.Serialization>  
 <span data-ttu-id="0edba-136">개체를 serialize하거나 deserialize하는 데 사용할 수 있는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-136">Contains classes that can be used for serializing and deserializing objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0edba-137">관련 단원</span><span class="sxs-lookup"><span data-stu-id="0edba-137">Related sections</span></span>  
 [<span data-ttu-id="0edba-138">XML 및 SOAP serialization</span><span class="sxs-lookup"><span data-stu-id="0edba-138">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 <span data-ttu-id="0edba-139">공용 언어 런타임에 포함된 XML serialization 메커니즘을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-139">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>  
  
 [<span data-ttu-id="0edba-140">보안 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="0edba-140">Security and Serialization</span></span>](../../../docs/framework/misc/security-and-serialization.md)  
 <span data-ttu-id="0edba-141">serialization을 수행하는 코드를 쓸 때 따를 보안 코딩 지침을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-141">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>  
  
 [<span data-ttu-id="0edba-142">원격 개체</span><span class="sxs-lookup"><span data-stu-id="0edba-142">Remote Objects</span></span>](http://msdn.microsoft.com/en-us/515686e6-0a8d-42f7-8188-73abede57c58)  
 <span data-ttu-id="0edba-143">.NET Framework에서 원격 통신에 사용할 수 있는 다양한 통신 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-143">Describes the various communications methods available in the .NET Framework for remote communications.</span></span>  
  
 [<span data-ttu-id="0edba-144">ASP.NET 및 XML Web Service 클라이언트를 사용하여 만든 XML Web Services</span><span class="sxs-lookup"><span data-stu-id="0edba-144">XML Web Services Created Using ASP.NET and XML Web Service Clients</span></span>](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c)  
 <span data-ttu-id="0edba-145">ASP.NET을 사용하여 만든 XML Web services를 프로그래밍하는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0edba-145">Provides topics that describe and explain how to program XML Web services created using ASP.NET.</span></span>
