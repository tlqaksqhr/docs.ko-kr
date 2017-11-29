---
title: FTP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d7b169a6de494d10fa332ebf5f2aa315ae69653a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ftp"></a><span data-ttu-id="25959-102">FTP</span><span class="sxs-lookup"><span data-stu-id="25959-102">FTP</span></span>
<span data-ttu-id="25959-103">.NET Framework에서는 <xref:System.Net.FtpWebRequest> 및 <xref:System.Net.FtpWebResponse> 클래스를 사용한 FTP 프로토콜을 포괄적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="25959-103">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="25959-104">이러한 클래스는 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="25959-104">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="25959-105">대부분의 경우 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 클래스는 요청을 만드는 데 필요한 모든 것을 제공하지만, 속성으로 노출되는 FTP별 기능에 액세스해야 할 경우 이러한 클래스를 <xref:System.Net.FtpWebRequest> 또는 <xref:System.Net.FtpWebResponse>로 형식 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25959-105">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="25959-106">예제</span><span class="sxs-lookup"><span data-stu-id="25959-106">Examples</span></span>  
 <span data-ttu-id="25959-107">자세한 내용은 [방법: FTP를 사용하여 파일 다운로드](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [방법: FTP를 사용하여 파일 업로드](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md) 및 [방법: FTP로 디렉터리 내용 나열](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25959-107">For more information, see the following topics: [How to: Download Files with FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).</span></span>  
  
## <a name="ftp-and-proxies"></a><span data-ttu-id="25959-108">FTP 및 프록시</span><span class="sxs-lookup"><span data-stu-id="25959-108">FTP and proxies</span></span>  
 <span data-ttu-id="25959-109"><xref:System.Net.FtpWebRequest.Proxy%2A> 속성으로 지정되는 프록시가 HTTP 프로시인 경우 <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> 및 <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> 명령만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="25959-109">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25959-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25959-110">See Also</span></span>  
 [<span data-ttu-id="25959-111">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="25959-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="25959-112">네트워크 프로그래밍 샘플</span><span class="sxs-lookup"><span data-stu-id="25959-112">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)  
 [<span data-ttu-id="25959-113">FTP 클라이언트 기술 샘플</span><span class="sxs-lookup"><span data-stu-id="25959-113">FTP Client Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179557)  
 [<span data-ttu-id="25959-114">FTP 탐색기 기술 샘플</span><span class="sxs-lookup"><span data-stu-id="25959-114">FTP Explorer Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179569)  
 [<span data-ttu-id="25959-115">응용 프로그램 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="25959-115">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
