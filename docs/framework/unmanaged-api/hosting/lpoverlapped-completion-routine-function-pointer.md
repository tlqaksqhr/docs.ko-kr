---
title: "LPOVERLAPPED_COMPLETION_ROUTINE 함수 포인터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LPOVERLAPPED_COMPLETION_ROUTINE
api_location: mscoree.dll
api_type: COM
f1_keywords: LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords: LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4d50f2058796d4c5c900474cdcbe71d8a5a911ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a><span data-ttu-id="59672-102">LPOVERLAPPED_COMPLETION_ROUTINE 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="59672-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="59672-103">Overlapped는 호스트에 알리는 하는 함수를 가리키는 (즉, 비동기) 장치에 대 한 I/O 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="59672-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="59672-104">이 함수 포인터에서 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="59672-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59672-105">구문</span><span class="sxs-lookup"><span data-stu-id="59672-105">Syntax</span></span>  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59672-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59672-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="59672-107">[in] 장치; 닫힌 경우 오류 코드 값 그렇지 않으면이 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="59672-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="59672-108">장치를 닫으면 I/O 장치에 보류 중인 모든를 즉시 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="59672-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="59672-109">[in] I/O 작업에서 전송 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="59672-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="59672-110">[in] I/O 요청을 완료 하는 데 사용할 정보를 포함 하는 구조에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59672-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59672-111">설명</span><span class="sxs-lookup"><span data-stu-id="59672-111">Remarks</span></span>  
 <span data-ttu-id="59672-112">함수를 `LPOVERLAPPED_COMPLETION_ROUTINE` 지점은 콜백 함수 및 호스팅 응용 프로그램의 작성자가 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59672-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="59672-113">콜백 함수는 완료 된 I/O 요청을 처리 하기 위해 호스트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="59672-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59672-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59672-114">Requirements</span></span>  
 <span data-ttu-id="59672-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59672-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59672-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="59672-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="59672-117">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="59672-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="59672-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59672-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59672-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59672-119">See Also</span></span>  
 [<span data-ttu-id="59672-120">사용 되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="59672-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
