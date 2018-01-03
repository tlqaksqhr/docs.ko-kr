---
title: "MissingInteropDataException 클래스(.NET 네이티브)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: eab4bcf8-9f5f-4731-87d8-842748a6062a
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: caf3882b8ba9c684d4751cafb5719606125dd983
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="missinginteropdataexception-class-net-native"></a><span data-ttu-id="0b8eb-102">MissingInteropDataException 클래스(.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="0b8eb-102">MissingInteropDataException Class (.NET Native)</span></span>
<span data-ttu-id="0b8eb-103">**Windows 10의 Windows 앱용 .NET, [!INCLUDE[net_native](../../../includes/net-native-md.md)]에만 해당**</span><span class="sxs-lookup"><span data-stu-id="0b8eb-103">**.NET for Windows apps for Windows 10, [!INCLUDE[net_native](../../../includes/net-native-md.md)] only**</span></span>  
  
 <span data-ttu-id="0b8eb-104">수동 마샬링 메서드를 호출했는데 정적 분석 또는 런타임 지시문 파일에서 형식의 메타데이터를 찾을 수 없을 때 throw되는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-104">The exception that is thrown when a manual marshaling method is called, but metadata for a type isn't found by static analysis or in a runtime directives file.</span></span>  
  
 <span data-ttu-id="0b8eb-105">**네임스페이스:** System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="0b8eb-105">**Namespace:** System.Runtime.CompilerServices</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0b8eb-106">`MissingInteropDataException` 클래스는 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 도구 체인에서 내부용으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-106">The `MissingInteropDataException` class is intended solely for internal use by the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain.</span></span> <span data-ttu-id="0b8eb-107">이 클래스는 타사 코드에서 사용하면 안 되고 응용 프로그램 코드에서 예외를 처리하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-107">It is not intended for use in third-party code, nor should you handle the exception in your application code.</span></span> <span data-ttu-id="0b8eb-108">대신, [런타임 지시문 파일](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)에 항목을 추가하여 예외를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-108">Instead, you eliminate the exception by adding entries to your [runtime directives file](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span> <span data-ttu-id="0b8eb-109">자세한 내용은 설명 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-109">For more information, see the Remarks section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b8eb-110">구문</span><span class="sxs-lookup"><span data-stu-id="0b8eb-110">Syntax</span></span>  
 [!code-csharp[ProjectN#21](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missinginteropdataexception_syntax1.cs#21)]
 [!code-vb[ProjectN#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/projectn/vb/missinginteropdataexception_syntax1.vb#21)]  
  
 <span data-ttu-id="0b8eb-111">`MissingInteropDataException` 클래스의 멤버는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-111">The `MissingInteropDataException` class has the following members:</span></span>  
  
## <a name="constructors"></a><span data-ttu-id="0b8eb-112">생성자</span><span class="sxs-lookup"><span data-stu-id="0b8eb-112">Constructors</span></span>  
  
|<span data-ttu-id="0b8eb-113">생성자</span><span class="sxs-lookup"><span data-stu-id="0b8eb-113">Constructor</span></span>|<span data-ttu-id="0b8eb-114">설명</span><span class="sxs-lookup"><span data-stu-id="0b8eb-114">Description</span></span>|  
|-----------------|-----------------|  
|`public MissingInteropDataException(String resourceId, Type pertinentType)`|<span data-ttu-id="0b8eb-115">오류를 설명하는 시스템 제공 메시지의 ID와 데이터가 누락된 형식을 사용하여 `MissingInteropDataException` 클래스의 새 인스턴스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-115">Initializes a new instance of the `MissingInteropDataException` class by using the ID of a system-supplied message that describes the error and the type whose data is missing.</span></span> <span data-ttu-id="0b8eb-116">이 생성자는 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 도구 체인에서 내부용으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-116">This constructor is for internal use by the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain only.</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="0b8eb-117">속성</span><span class="sxs-lookup"><span data-stu-id="0b8eb-117">Properties</span></span>  
  
|<span data-ttu-id="0b8eb-118">속성</span><span class="sxs-lookup"><span data-stu-id="0b8eb-118">Property</span></span>|<span data-ttu-id="0b8eb-119">설명</span><span class="sxs-lookup"><span data-stu-id="0b8eb-119">Description</span></span>|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|<span data-ttu-id="0b8eb-120">예외에 대한 사용자 정의 추가 정보를 제공하는 키/값 쌍의 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-120">Gets a collection of key/value pairs that provide additional user-defined information about the exception.</span></span> <span data-ttu-id="0b8eb-121"><xref:System.Exception?displayProperty=nameWithType>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-121">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public string HelpLink { get; set; }`|<span data-ttu-id="0b8eb-122">이 예외와 연결된 도움말 파일에 대한 링크를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-122">Gets or sets a link to the help file associated with this exception.</span></span> <span data-ttu-id="0b8eb-123"><xref:System.Exception?displayProperty=nameWithType>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-123">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public int HResult { get; protected set; }`|<span data-ttu-id="0b8eb-124">특정 예외에 할당되는 코딩된 숫자 값인 `HRESULT`를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-124">Gets or sets the `HRESULT`, which is a coded numeric value that is assigned to a specific exception.</span></span> <span data-ttu-id="0b8eb-125"><xref:System.Exception?displayProperty=nameWithType>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-125">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public Exception InnerException { get; }`|<span data-ttu-id="0b8eb-126">현재 예외를 발생시킨 예외를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-126">Gets the exception that caused the current exception.</span></span> <span data-ttu-id="0b8eb-127"><xref:System.Exception?displayProperty=nameWithType>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-127">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public string Message { get; }`|<span data-ttu-id="0b8eb-128">현재 예외를 설명하는 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-128">Gets a message that describes the current exception.</span></span> <span data-ttu-id="0b8eb-129"><xref:System.Exception?displayProperty=nameWithType>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-129">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public Type MissingType { get; private set; }`|<span data-ttu-id="0b8eb-130">데이터가 누락된 형식을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-130">Gets or sets the type whose data is missing.</span></span>|  
|`public string Source { get; set; }`|<span data-ttu-id="0b8eb-131">오류를 발생시킨 앱 또는 개체의 이름을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-131">Gets or sets the name of the app or object that caused the error.</span></span> <span data-ttu-id="0b8eb-132"><xref:System.Exception?displayProperty=nameWithType>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-132">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public string StackTrace { get; }`|<span data-ttu-id="0b8eb-133">호출 스택의 직접 실행 프레임 문자열 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-133">Gets a string representation of the immediate frames on the call stack.</span></span> <span data-ttu-id="0b8eb-134"><xref:System.Exception?displayProperty=nameWithType>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-134">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public MethodBase TargetSite { get; }`|<span data-ttu-id="0b8eb-135">현재 예외가 throw된 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-135">Gets the method that threw the current exception.</span></span> <span data-ttu-id="0b8eb-136"><xref:System.Exception?displayProperty=nameWithType>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-136">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
  
## <a name="methods"></a><span data-ttu-id="0b8eb-137">메서드</span><span class="sxs-lookup"><span data-stu-id="0b8eb-137">Methods</span></span>  
  
|<span data-ttu-id="0b8eb-138">메서드</span><span class="sxs-lookup"><span data-stu-id="0b8eb-138">Method</span></span>|<span data-ttu-id="0b8eb-139">설명</span><span class="sxs-lookup"><span data-stu-id="0b8eb-139">Description</span></span>|  
|------------|-----------------|  
|`public bool Equals(Object obj)`|<span data-ttu-id="0b8eb-140">지정한 개체와 현재 개체가 같은지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-140">Determines whether the specified object is equal to the current object.</span></span>  <span data-ttu-id="0b8eb-141"><xref:System.Object>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-141">(Inherited from <xref:System.Object>.)</span></span>|  
|`protected void Finalize()`|<span data-ttu-id="0b8eb-142">가비지 수집기가 회수하기 전에 개체가 리소스를 해제하고 다른 정리 작업을 수행할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-142">Allows an object to try to free resources and perform other cleanup operations before it is reclaimed by garbage collection.</span></span> <span data-ttu-id="0b8eb-143"><xref:System.Object>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-143">(Inherited from <xref:System.Object>.)</span></span>|  
|`public Exception GetBaseException()`|<span data-ttu-id="0b8eb-144">후속 예외 하나 이상의 근본 원인이 되는 예외를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-144">Returns the exception that is the root cause of one or more subsequent exceptions.</span></span> <span data-ttu-id="0b8eb-145"><xref:System.Exception?displayProperty=nameWithType>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-145">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public int GetHashCode()`|<span data-ttu-id="0b8eb-146">`MissingInteropDataException` 인스턴스의 해시 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-146">Returns a hash code for a `MissingInteropDataException` instance.</span></span>   <span data-ttu-id="0b8eb-147"><xref:System.Object>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-147">(Inherited from <xref:System.Object>.)</span></span>|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|<span data-ttu-id="0b8eb-148">예외에 대한 정보를 사용하여 <xref:System.Runtime.Serialization.SerializationInfo> 개체를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-148">Sets a <xref:System.Runtime.Serialization.SerializationInfo> object with information about the exception.</span></span>  <span data-ttu-id="0b8eb-149"><xref:System.Exception?displayProperty=nameWithType>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-149">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public Type GetType()`|<span data-ttu-id="0b8eb-150">현재 인스턴스의 런타임 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-150">Gets the runtime type of the current instance.</span></span> <span data-ttu-id="0b8eb-151"><xref:System.Exception?displayProperty=nameWithType>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-151">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`protected Object MemberwiseClone()`|<span data-ttu-id="0b8eb-152">현재 개체의 부분 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-152">Creates a shallow copy of the current object.</span></span> <span data-ttu-id="0b8eb-153"><xref:System.Object>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-153">(Inherited from <xref:System.Object>.)</span></span>|  
|`public string ToString()`|<span data-ttu-id="0b8eb-154">현재 예외의 문자열 표현을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-154">Returns the string representation of the current exception.</span></span> <span data-ttu-id="0b8eb-155"><xref:System.Exception?displayProperty=nameWithType>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-155">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
  
## <a name="events"></a><span data-ttu-id="0b8eb-156">이벤트</span><span class="sxs-lookup"><span data-stu-id="0b8eb-156">Events</span></span>  
  
|<span data-ttu-id="0b8eb-157">Event</span><span class="sxs-lookup"><span data-stu-id="0b8eb-157">Event</span></span>|<span data-ttu-id="0b8eb-158">설명</span><span class="sxs-lookup"><span data-stu-id="0b8eb-158">Description</span></span>|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|<span data-ttu-id="0b8eb-159">예외에 대한 serialize된 데이터를 포함하는 예외 상태 개체를 만들기 위해 예외를 serialize할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-159">Occurs when an exception is serialized to create an exception state object that contains serialized data about the exception.</span></span> <span data-ttu-id="0b8eb-160"><xref:System.Exception?displayProperty=nameWithType>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-160">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
  
## <a name="usage-details"></a><span data-ttu-id="0b8eb-161">자세한 용도</span><span class="sxs-lookup"><span data-stu-id="0b8eb-161">Usage Details</span></span>  
 <span data-ttu-id="0b8eb-162">형식 정보를 사용할 수 없어 COM 또는 Windows 런타임 구성 요소에 대한 메서드 호출을 정상적으로 수행할 수 없으면 `MissingInteropDataException` 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-162">The `MissingInteropDataException` exception is thrown when a method call to a COM or Windows Runtime component cannot be made successfully because type information isn't available.</span></span>  
  
 <span data-ttu-id="0b8eb-163">런타임에 앱이 사용할 수 있는 메타데이터는 런타임 지시문(XML 구성) 파일인 *.rd.xml을 통해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-163">The metadata that is available to an app at run time is defined by the runtime directives (XML configuration) file, *.rd.xml.</span></span> <span data-ttu-id="0b8eb-164">앱에서 이 예외가 throw되지 않도록 하려면 런타임에 존재해야 하는 메타데이터를 정의하도록 이 파일을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-164">To prevent your app from throwing this exception, you must modify this file to define the metadata that must be present at run time.</span></span> <span data-ttu-id="0b8eb-165">런타임 지시문 파일에서 해당 프로그램 요소에 `MarshalObject`, `MarshalDelegate` 또는 `MarshalStructure` 특성을 추가하여 이 오류를 해결하는 방식이 가장 일반적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-165">Most commonly, you address this error by adding a `MarshalObject`, `MarshalDelegate`, or `MarshalStructure` attribute to an appropriate program element in the runtime directives file.</span></span> <span data-ttu-id="0b8eb-166">이 파일 형식에 대한 자세한 내용은 [런타임 지시문(rd.xml) 구성 파일 참조](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-166">For information about the format of this file, see [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0b8eb-167">이 예외는 응용 프로그램에 필요한 메타데이터를 런타임에 사용할 수 없음을 나타내므로 `try`/`catch` 블록에서 이 예외를 처리하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-167">Because this exception indicates that metadata needed by your application isn’t available at run time, you shouldn’t handle this exception in a `try`/`catch` block.</span></span> <span data-ttu-id="0b8eb-168">대신 예외의 원인을 진단하고 런타임 지시문 파일에 적절한 항목을 추가하여 예외를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-168">Instead, you should diagnose the cause of the exception and eliminate it by adding the appropriate entry to a runtime directives file.</span></span>  
  
 <span data-ttu-id="0b8eb-169">`MissingInteropDataException` 클래스는 메서드를 정상적으로 호출하려면 해당 메타데이터가 필요한 형식을 나타내는 고유한 멤버 하나(`MissingType` 속성)를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-169">The `MissingInteropDataException` class contains a single unique member, the `MissingType` property, that indicates the type whose metadata is needed for a successful method call.</span></span> <span data-ttu-id="0b8eb-170">나머지 모든 멤버는 기본 클래스인 <xref:System.Exception?displayProperty=nameWithType>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b8eb-170">All remaining members are inherited from the base class, <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b8eb-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b8eb-171">See Also</span></span>  
 <xref:System.Exception?displayProperty=nameWithType>  
 [<span data-ttu-id="0b8eb-172">MissingMetadataException 클래스</span><span class="sxs-lookup"><span data-stu-id="0b8eb-172">MissingMetadataException Class</span></span>](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)  
 [<span data-ttu-id="0b8eb-173">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="0b8eb-173">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
