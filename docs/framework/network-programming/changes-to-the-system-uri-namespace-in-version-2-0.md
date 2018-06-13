---
title: 버전 2.0에서 System.Uri 네임스페이스 변경 내용
ms.date: 03/30/2017
ms.assetid: 35883fe9-2d09-4d8b-80ca-cf23a941e459
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 169454edd04bfdb55affcc2be12140f42dd2f7ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33392450"
---
# <a name="changes-to-the-systemuri-namespace-in-version-20"></a><span data-ttu-id="80155-102">버전 2.0에서 System.Uri 네임스페이스 변경 내용</span><span class="sxs-lookup"><span data-stu-id="80155-102">Changes to the System.Uri namespace in Version 2.0</span></span>
<span data-ttu-id="80155-103"><xref:System.Uri?displayProperty=nameWithType> 클래스에 몇 가지 변경 내용이 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80155-103">Several changes were made to the <xref:System.Uri?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="80155-104">이러한 변경 내용은 잘못된 동작을 수정하고, 유용성을 개선하고, 보안을 강화했습니다.</span><span class="sxs-lookup"><span data-stu-id="80155-104">These changes fixed incorrect behavior, enhanced usability, and enhanced security.</span></span>  
  
## <a name="obsolete-and-deprecated-members"></a><span data-ttu-id="80155-105">더 이상 사용되지 않는 멤버</span><span class="sxs-lookup"><span data-stu-id="80155-105">Obsolete and Deprecated Members</span></span>  
 <span data-ttu-id="80155-106">생성자:</span><span class="sxs-lookup"><span data-stu-id="80155-106">Constructors:</span></span>  
  
-   <span data-ttu-id="80155-107">`dontEscape` 매개 변수가 있는 모든 생성자.</span><span class="sxs-lookup"><span data-stu-id="80155-107">All constructors that have a `dontEscape` parameter.</span></span>  
  
 <span data-ttu-id="80155-108">메서드:</span><span class="sxs-lookup"><span data-stu-id="80155-108">Methods:</span></span>  
  
-   <xref:System.Uri.CheckSecurity%2A>  
  
-   <xref:System.Uri.Escape%2A>  
  
-   <xref:System.Uri.Canonicalize%2A>  
  
-   <xref:System.Uri.Parse%2A>  
  
-   <xref:System.Uri.IsReservedCharacter%2A>  
  
-   <xref:System.Uri.IsBadFileSystemCharacter%2A>  
  
-   <xref:System.Uri.IsExcludedCharacter%2A>  
  
-   <xref:System.Uri.EscapeString%2A>  
  
## <a name="changes"></a><span data-ttu-id="80155-109">변경 내용</span><span class="sxs-lookup"><span data-stu-id="80155-109">Changes</span></span>  
  
-   <span data-ttu-id="80155-110">쿼리 부분(file, ftp 등)이 없는 것으로 알려진 URI 체계에서는 ‘?’ 문자가 항상 이스케이프되고 <xref:System.Uri.Query%2A> 부분의 시작으로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80155-110">For URI schemes that are known to not have a query part (file, ftp, and others), the '?' character is always escaped and is not considered the beginning of a <xref:System.Uri.Query%2A> part.</span></span>  
  
-   <span data-ttu-id="80155-111">암시적 파일 URI(“c:\directory\file@name.txt” 형식)의 경우 전체 이스케이프 취소가 요청되거나 <xref:System.Uri.LocalPath%2A>가 `true`인 경우가 아니면 조각 문자(‘#’)가 항상 이스케이프됩니다.</span><span class="sxs-lookup"><span data-stu-id="80155-111">For implicit file URIs (of the form "c:\directory\file@name.txt"), the fragment character ('#') is always escaped unless full unescaping is requested or <xref:System.Uri.LocalPath%2A> is `true`.</span></span>  
  
-   <span data-ttu-id="80155-112">UNC 호스트 이름 지원이 제거되었습니다. 국제 호스트 이름을 나타내기 위한 IDN 사양이 채택되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80155-112">UNC hostname support was removed; the IDN specification for representing international hostnames was adopted.</span></span>  
  
-   <span data-ttu-id="80155-113"><xref:System.Uri.LocalPath%2A>는 항상 완전히 이스케이프 해제된 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="80155-113"><xref:System.Uri.LocalPath%2A> always returns a completely unescaped string.</span></span>  
  
-   <span data-ttu-id="80155-114"><xref:System.Uri.ToString%2A>은 이스케이프된 ‘%’, ‘?’ 또는 ‘#’ 문자의 이스케이프를 해제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80155-114"><xref:System.Uri.ToString%2A> does not unescape an escaped '%', '?', or '#' character.</span></span>  
  
-   <span data-ttu-id="80155-115">이제 <xref:System.Uri.Equals%2A>의 동등성 검사에 <xref:System.Uri.Query%2A> 부분이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="80155-115"><xref:System.Uri.Equals%2A> now includes the <xref:System.Uri.Query%2A> part in the equality check.</span></span>  
  
-   <span data-ttu-id="80155-116">연산자 “= =” 및 “!=”가 재정의되고 <xref:System.Uri.Equals%2A> 메서드에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="80155-116">Operators "==" and "!=" are overridden and linked to the <xref:System.Uri.Equals%2A> method.</span></span>  
  
-   <span data-ttu-id="80155-117">이제 <xref:System.Uri.IsLoopback%2A>에서 일관된 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="80155-117"><xref:System.Uri.IsLoopback%2A> now produces consistent results.</span></span>  
  
-   <span data-ttu-id="80155-118">URI “`file:///path`”가 더 이상 “file://path”로 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80155-118">The URI "`file:///path`" is no longer translated into "file://path".</span></span>  
  
-   <span data-ttu-id="80155-119">아재 “#”이 호스트 이름 종결자로 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="80155-119">"#" is now recognized as a host name terminator.</span></span> <span data-ttu-id="80155-120">즉, "http://consoto.com#fragment"는 이제 "http://contoso.com/#fragment"로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="80155-120">That is, "http://consoto.com#fragment" is now converted to "http://contoso.com/#fragment".</span></span>  
  
-   <span data-ttu-id="80155-121">기본 URI와 조각을 결합할 때 발생하는 버그가 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80155-121">A bug when combining a base URI with a fragment has been fixed.</span></span>  
  
-   <span data-ttu-id="80155-122"><xref:System.Uri.HostNameType%2A>의 버그가 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80155-122">A bug in <xref:System.Uri.HostNameType%2A> is fixed.</span></span>  
  
-   <span data-ttu-id="80155-123">NNTP 구문 분석의 버그가 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80155-123">A bug in NNTP parsing is fixed.</span></span>  
  
-   <span data-ttu-id="80155-124">이제 HTTP:contoso.com 형식의 URI가 구문 분석 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="80155-124">A URI of the form HTTP:contoso.com now throws a parsing exception.</span></span>  
  
-   <span data-ttu-id="80155-125">프레임워크에서 URI의 사용자 정보를 올바르게 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="80155-125">The Framework correctly handles userinfo in a URI.</span></span>  
  
-   <span data-ttu-id="80155-126">끊어진 URI가 루트 위의 파일 시스템을 트래버스할 수 없도록 URI 경로 압축이 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80155-126">URI path compression is fixed so that a broken URI cannot traverse the file system above the root.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80155-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80155-127">See Also</span></span>  
 <xref:System.Uri?displayProperty=nameWithType>
