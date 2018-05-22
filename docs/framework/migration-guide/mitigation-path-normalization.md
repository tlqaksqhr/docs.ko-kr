---
title: '완화: 경로 정규화'
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36433dcce1e47b329f5407e86ce3923a44cb6444
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="5e115-102">완화: 경로 정규화</span><span class="sxs-lookup"><span data-stu-id="5e115-102">Mitigation: Path Normalization</span></span>
<span data-ttu-id="5e115-103">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]을 대상으로 하는 앱부터, .NET Framework의 경로 정규화가 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5e115-103">Starting with apps the target  the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="5e115-104">경로 정규화란?</span><span class="sxs-lookup"><span data-stu-id="5e115-104">What is path normalization?</span></span>  
 <span data-ttu-id="5e115-105">경로 정규화 중에는 대상 운영 체제의 올바른 경로에 맞게 경로 또는 파일을 식별하는 문자열이 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e115-105">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="5e115-106">정규화에는 일반적으로 다음이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e115-106">Normalization typically involves:</span></span>  
  
-   <span data-ttu-id="5e115-107">구성 요소 및 디렉터리 구분 기호 정규화</span><span class="sxs-lookup"><span data-stu-id="5e115-107">Canonicalizing component and directory separators.</span></span>  
  
-   <span data-ttu-id="5e115-108">상대 경로에 현재 디렉터리 적용</span><span class="sxs-lookup"><span data-stu-id="5e115-108">Applying the current directory to a relative path.</span></span>  
  
-   <span data-ttu-id="5e115-109">경로의 상대 디렉터리(`.`) 또는 부모 디렉터리(`..`) 평가</span><span class="sxs-lookup"><span data-stu-id="5e115-109">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
-   <span data-ttu-id="5e115-110">지정된 문자 자르기</span><span class="sxs-lookup"><span data-stu-id="5e115-110">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="5e115-111">변경 내용</span><span class="sxs-lookup"><span data-stu-id="5e115-111">The changes</span></span>  
 <span data-ttu-id="5e115-112">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터, 경로 정규화가 다음과 같이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5e115-112">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], path normalization has changed in the following ways:</span></span>  
  
-   <span data-ttu-id="5e115-113">런타임은 운영 체제의 [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963\(v=vs.85\).aspx) 함수를 지연시켜 경로를 정규화합니다.</span><span class="sxs-lookup"><span data-stu-id="5e115-113">The runtime defers to the operating system's [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963\(v=vs.85\).aspx) function to normalize paths.</span></span>  
  
-   <span data-ttu-id="5e115-114">정규화 중에 더 이상 디렉터리 세그먼트의 끝(예: 디렉터리 이름 끝의 공백)이 잘리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e115-114">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
-   <span data-ttu-id="5e115-115">완전 신뢰의 장치 경로 구문(`\\.\` 포함) 지원 및 mscorlib.dll `\\?\`에서 파일 I/O API 지원</span><span class="sxs-lookup"><span data-stu-id="5e115-115">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
-   <span data-ttu-id="5e115-116">런타임에서 장치 구문 경로가 유효한지 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e115-116">The runtime does not validate device syntax paths.</span></span>  
  
-   <span data-ttu-id="5e115-117">대체 데이터 스트림에 액세스하기 위해 장치 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e115-117">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="5e115-118">영향</span><span class="sxs-lookup"><span data-stu-id="5e115-118">Impact</span></span>  
 <span data-ttu-id="5e115-119">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이상 버전을 대상으로 하는 앱의 경우 이러한 변경이 기본적으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e115-119">For apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later, these changes are on  by default.</span></span> <span data-ttu-id="5e115-120">이를 통해 메서드에서 이전에 액세스할 수 없는 경로에 액세스할 수 있게 되었으며 성능이 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5e115-120">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
 <span data-ttu-id="5e115-121">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 및 이전 버전을 대상으로 하지만 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이상에서 실행되는 앱은 이러한 변경에 의해 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e115-121">Apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions but are running under the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="5e115-122">완화</span><span class="sxs-lookup"><span data-stu-id="5e115-122">Mitigation</span></span>  
 <span data-ttu-id="5e115-123">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이상을 대상으로 하는 앱은 애플리케이션 구성 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음을 추가하여 이 동작을 옵트아웃(Opt out)하고 레거시 정규화를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e115-123">Apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
 <span data-ttu-id="5e115-124">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 또는 이전 버전을 대상으로 하지만 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이상이 실행되는 앱은 응용 프로그램 .configuration 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음을 추가하여 경로 정규화에 대한 변경을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e115-124">Apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or earlier but are running on the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e115-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e115-125">See Also</span></span>  
 [<span data-ttu-id="5e115-126">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="5e115-126">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
