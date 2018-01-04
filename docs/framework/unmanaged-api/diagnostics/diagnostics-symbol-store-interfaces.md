---
title: "진단 기호 저장소 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9a9550bf1e3e5500356584b1bdd53f5d3061e190
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="f20d6-102">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="f20d6-103">이 항목에서는 컴파일러가 디버거에 사용에 대 한 기호 정보를 생성 하는 데 사용할 수 있는 관리 되지 않는 인터페이스에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f20d6-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f20d6-104">In This Section</span></span>  
 [<span data-ttu-id="f20d6-105">IBindingDisplay 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="f20d6-106">실행 중인 응용 프로그램에 대 한 현재 바인딩 정보를 표시 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="f20d6-107">IDebugAutoAttach 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="f20d6-108">서버에서 호출한 디버거 자동 연결에 대 한 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="f20d6-109">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="f20d6-110">등록 및 연결 알림 소스를 등록 취소 하기 위한 메서드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="f20d6-111">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="f20d6-112">싱크 알림 위한 메서드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="f20d6-113">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="f20d6-114">알림 필터를 설정 하기 위한 메서드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="f20d6-115">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="f20d6-116">편집 하며 계속 하기 기능에 대 한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="f20d6-117">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="f20d6-118">이 인터페이스는 읽기 보완 하 [ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="f20d6-119">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="f20d6-120">선택적 async 메서드 정보 메서드 기호 당의 정의 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="f20d6-121">열린된 메서드와 함께 사용 해야 합니다 (즉, 호출 하는 사이 [OpenMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)및 [CloseMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="f20d6-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="f20d6-122">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="f20d6-123">비관리 코드의 기호 바인더를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="f20d6-124">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="f20d6-125">비관리 코드의 기호 바인더를 나타내며 확장는 `ISymUnmanagedBinder` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="f20d6-126">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="f20d6-127">비관리 코드의 기호 바인더를 나타내며 확장는 `ISymUnmanagedBinder` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="f20d6-128">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="f20d6-129">관리 되지 않는 상수에 대 한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="f20d6-130">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="f20d6-131">관리 되지 않는 리소스를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="f20d6-132">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="f20d6-133">기호 저장소가 참조하는 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="f20d6-134">ISymUnmanagedDocumentWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="f20d6-135">기호 저장소가 참조하는 문서에 쓰기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="f20d6-136">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="f20d6-137">편집 하며 계속 하기 기능에 대 한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="f20d6-138">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="f20d6-139">기호 저장소 내의 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="f20d6-140">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="f20d6-141">네임 스페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="f20d6-142">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="f20d6-143">문서, 메서드 및 기호 저장소 내의 변수에 대 한 액세스를 제공 하는 기호 판독기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="f20d6-144">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="f20d6-145">메서드 토큰 및 편집 복사 버전 번호가 지정 된 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="f20d6-146">ISymUnmanagedReaderSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="f20d6-147">기호 검색 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="f20d6-148">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="f20d6-149">메서드에 들어 있는 어휘 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="f20d6-150">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="f20d6-151">메서드에 들어 있는 어휘 범위를 나타내며 확장는 `ISymUnmanagedScope` 범위 내에서 정의 된 상수에 대 한 정보를 가져오는 메서드를 사용 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="f20d6-152">ISymUnmanagedSourceServerModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="f20d6-153">모듈에 대 한 원본 서버 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="f20d6-154">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="f20d6-155">검색 경로 대 한 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="f20d6-156">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="f20d6-157">매개 변수, 지역 변수 또는 필드와 같은 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="f20d6-158">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="f20d6-159">기호 작성기를 나타내며 문서 "," 시퀀스 위치 "," 어휘 범위 "및" 변수를 정의 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="f20d6-160">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="f20d6-161">기호 작성기를 나타내며 문서 "," 시퀀스 위치 "," 어휘 범위 "및" 변수를 정의 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="f20d6-162">확장 된 `ISymUnmanagedWriter` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="f20d6-163">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="f20d6-164">기호 작성기를 나타내며 문서 "," 시퀀스 위치 "," 어휘 범위 "및" 변수를 정의 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="f20d6-165">확장 된 `ISymUnmanagedWriter` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="f20d6-166">ISymUnmanagedWriter4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="f20d6-167">ISymUnmanagedWriter4 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="f20d6-168">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20d6-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="f20d6-169">ISymUnmanagedWriter5 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f20d6-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f20d6-170">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f20d6-170">Related Sections</span></span>  
 [<span data-ttu-id="f20d6-171">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="f20d6-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="f20d6-172">진단 기호 저장소 구조체</span><span class="sxs-lookup"><span data-stu-id="f20d6-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="f20d6-173">디버깅</span><span class="sxs-lookup"><span data-stu-id="f20d6-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
