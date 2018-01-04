---
title: "방법: SSL 인증서를 사용하여 포트 구성"
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
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3fbd3b640e90ecf0ff5857bd33465e8c60135eac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="9dfef-102">방법: SSL 인증서를 사용하여 포트 구성</span><span class="sxs-lookup"><span data-stu-id="9dfef-102">How to: Configure a Port with an SSL Certificate</span></span>
<span data-ttu-id="9dfef-103">전송 보안을 사용하는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클래스에 자체 호스트된 <xref:System.ServiceModel.WSHttpBinding> 서비스를 만드는 경우에는 X.509 인증서로 포트도 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-103">When creating a self-hosted [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="9dfef-104">자체 호스트된 서비스를 만들지 않는 경우에는 IIS(인터넷 정보 서비스)에서 서비스를 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="9dfef-105">[HTTP 전송 보안](../../../../docs/framework/wcf/feature-details/http-transport-security.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-105"> [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="9dfef-106">포트를 구성하려면 컴퓨터에서 실행하는 운영 체제에 따라 다른 도구를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="9dfef-107">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 또는 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]를 실행하는 경우 HttpCfg.exe 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-107">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool.</span></span> <span data-ttu-id="9dfef-108">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]에는 이 도구가 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-108">With [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] this tool is installed.</span></span> <span data-ttu-id="9dfef-109">와 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]에서 도구를 다운로드할 수 있습니다 [Windows XP 서비스 팩 2 지원 도구](http://go.microsoft.com/fwlink/?LinkId=88606)합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-109">With [!INCLUDE[wxp](../../../../includes/wxp-md.md)], you can download the tool at [Windows XP Service Pack 2 Support Tools](http://go.microsoft.com/fwlink/?LinkId=88606).</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="9dfef-110">[Httpcfg 개요](http://go.microsoft.com/fwlink/?LinkId=88605)합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-110"> [Httpcfg Overview](http://go.microsoft.com/fwlink/?LinkId=88605).</span></span> <span data-ttu-id="9dfef-111">[Windows 지원 도구 설명서](http://go.microsoft.com/fwlink/?LinkId=94840) Httpcfg.exe 도구에 대 한 구문에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-111">The [Windows Support Tools documentation](http://go.microsoft.com/fwlink/?LinkId=94840) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="9dfef-112">[!INCLUDE[wv](../../../../includes/wv-md.md)]를 실행하는 경우 이미 설치되어 있는 Netsh.exe 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-112">If you are running [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool that is already installed.</span></span>  
  
 <span data-ttu-id="9dfef-113">이 항목에서는 다음과 같은 여러 절차를 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-113">This topic describes how to accomplish several procedures:</span></span>  
  
-   <span data-ttu-id="9dfef-114">컴퓨터의 현재 포트 구성 결정</span><span class="sxs-lookup"><span data-stu-id="9dfef-114">Determining a computer's current port configuration.</span></span>  
  
-   <span data-ttu-id="9dfef-115">인증서의 지문 가져오기(다음 두 절차에 필요)</span><span class="sxs-lookup"><span data-stu-id="9dfef-115">Getting a certificate's thumbprint (necessary for the following two procedures).</span></span>  
  
-   <span data-ttu-id="9dfef-116">SSL 인증서를 포트 구성에 바인딩</span><span class="sxs-lookup"><span data-stu-id="9dfef-116">Binding an SSL certificate to a port configuration.</span></span>  
  
-   <span data-ttu-id="9dfef-117">SSL 인증서를 포트 구성에 바인딩 및 클라이언트 인증서 지원</span><span class="sxs-lookup"><span data-stu-id="9dfef-117">Binding an SSL certificate to a port configuration and supporting client certificates.</span></span>  
  
-   <span data-ttu-id="9dfef-118">포트 번호에서 SSL 인증서 삭제</span><span class="sxs-lookup"><span data-stu-id="9dfef-118">Deleting an SSL certificate from a port number.</span></span>  
  
 <span data-ttu-id="9dfef-119">컴퓨터에 저장된 인증서를 수정하려면 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-119">Note that modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
### <a name="to-determine-how-ports-are-configured"></a><span data-ttu-id="9dfef-120">포트의 구성 방법을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="9dfef-120">To determine how ports are configured</span></span>  
  
1.  <span data-ttu-id="9dfef-121">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 또는 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]를 HttpCfg.exe 도구를 사용 하 여 현재 포트 구성을 보려면 사용 하 여는 **쿼리** 및 **ssl** 스위치, 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-121">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```  
    httpcfg query ssl  
    ```  
  
2.  <span data-ttu-id="9dfef-122">[!INCLUDE[wv](../../../../includes/wv-md.md)]에서 다음 예제와 같이 Netsh.exe 도구를 사용하여 현재 포트 구성을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-122">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a><span data-ttu-id="9dfef-123">인증서의 지문을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="9dfef-123">To get a certificate's thumbprint</span></span>  
  
1.  <span data-ttu-id="9dfef-124">인증서 MMC 스냅인을 사용하여 클라이언트 인증 용도의 X.509 인증서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-124">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="9dfef-125">[하는 방법: MMC 스냅인을 사용 하 여 인증서 보기](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-125"> [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2.  <span data-ttu-id="9dfef-126">인증서의 지문에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-126">Access the certificate's thumbprint.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="9dfef-127">[하는 방법: 인증서의 지문을 검색](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-127"> [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3.  <span data-ttu-id="9dfef-128">인증서의 지문을 메모장 등의 텍스트 편집기에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-128">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4.  <span data-ttu-id="9dfef-129">16진수 문자 사이의 모든 공간을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-129">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="9dfef-130">여기에 사용되는 방법 중 하나는 텍스트 편집기의 찾기 및 바꾸기 기능을 사용하여 각 공간을 null 문자로 바꾸는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-130">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="9dfef-131">SSL 인증서를 포트 번호에 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="9dfef-131">To bind an SSL certificate to a port number</span></span>  
  
1.  <span data-ttu-id="9dfef-132">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 또는 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]에서 SSL(Secure Sockets Layer) 저장소에 "set" 모드의 HttpCfg.exe 도구를 사용하여 인증서를 포트 번호에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-132">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="9dfef-133">도구에서는 다음 예제처럼 지문을 사용하여 인증서를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-133">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    -   <span data-ttu-id="9dfef-134">**-i** 스위치는 구문이 `IP`:`port` 및 컴퓨터의 포트 8012에 인증서를 설정 하도록 도구에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-134">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="9dfef-135">선택적으로, 번호 앞에 있는 4개의 0을 컴퓨터의 실제 IP 주소로 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-135">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    -   <span data-ttu-id="9dfef-136">**-h** 스위치는 인증서의 지문을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-136">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2.  <span data-ttu-id="9dfef-137">[!INCLUDE[wv](../../../../includes/wv-md.md)]에서 다음 예제와 같이 Netsh.exe 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-137">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    -   <span data-ttu-id="9dfef-138">**certhash** 매개 변수는 인증서의 지문을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-138">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    -   <span data-ttu-id="9dfef-139">**다음과 유사** 매개 변수는 IP 주소 및 포트를 지정 하 고과 똑같이 작동은 **-i** 설명한 Httpcfg.exe 도구의 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-139">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    -   <span data-ttu-id="9dfef-140">**appid** 매개 변수는 소유 응용 프로그램을 식별 하는 데 사용할 수 있는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-140">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="9dfef-141">SSL 인증서를 포트 번호에 바인딩하고 클라이언트 인증서를 지원하려면</span><span class="sxs-lookup"><span data-stu-id="9dfef-141">To bind an SSL certificate to a port number and support client certificates</span></span>  
  
1.  <span data-ttu-id="9dfef-142">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 또는 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]에서 전송 계층에 X.509 인증서를 사용하여 인증하는 클라이언트를 지원하려면 위의 절차를 수행하되 다음 예제처럼 추가 명령줄 매개 변수를 HttpCfg.exe에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-142">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="9dfef-143">**-f** 스위치는 구문이 `n` 여기서 n은 1에서 7 사이의 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-143">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="9dfef-144">위의 예제와 같이 값 2를 사용하면 전송 계층에서 클라이언트 인증서가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-144">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="9dfef-145">값 3을 사용하면 클라이언트 인증서가 활성화되고 해당 인증서가 Windows 계정에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-145">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="9dfef-146">다른 값의 동작에 대한 자세한 내용은 HttpCfg.exe 도움말을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9dfef-146">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2.  <span data-ttu-id="9dfef-147">[!INCLUDE[wv](../../../../includes/wv-md.md)]에서 전송 계층에서 X.509 인증서를 사용하여 인증하는 클라이언트를 지원하려면 위의 절차를 수행하되 다음 예제처럼 추가 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-147">In [!INCLUDE[wv](../../../../includes/wv-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="9dfef-148">포트 번호에서 SSL 인증서를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="9dfef-148">To delete an SSL certificate from a port number</span></span>  
  
1.  <span data-ttu-id="9dfef-149">HttpCfg.exe 또는 Netsh.exe 도구를 사용하여 컴퓨터에 있는 모든 바인딩의 포트와 지문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-149">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="9dfef-150">정보를 디스크에 인쇄하려면 다음 예제와 같이 리디렉션 문자 ">"를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-150">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```  
    httpcfg query ssl>myMachinePorts.txt  
    ```  
  
2.  <span data-ttu-id="9dfef-151">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 또는 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]를 사용 하 여 HttpCfg.exe 도구를 사용 하 여는 **삭제** 및 **ssl** 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-151">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="9dfef-152">사용 하 여는 **-i** 지정 하는 스위치는 `IP`:`port` 번호 및 **-h** 지문이 지정 하는 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-152">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3.  <span data-ttu-id="9dfef-153">[!INCLUDE[wv](../../../../includes/wv-md.md)]에서 다음 예제와 같이 Netsh.exe 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-153">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="9dfef-154">예</span><span class="sxs-lookup"><span data-stu-id="9dfef-154">Example</span></span>  
 <span data-ttu-id="9dfef-155">다음 코드에서는 전송 보안에 설정된 <xref:System.ServiceModel.WSHttpBinding> 클래스를 사용하여 자체 호스트된 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-155">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="9dfef-156">응용 프로그램을 만들 때에는 주소에 포트 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfef-156">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9dfef-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9dfef-157">See Also</span></span>  
 [<span data-ttu-id="9dfef-158">HTTP 전송 보안</span><span class="sxs-lookup"><span data-stu-id="9dfef-158">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
