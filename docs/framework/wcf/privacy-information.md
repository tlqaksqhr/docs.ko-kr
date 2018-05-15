---
title: Windows Communication Foundation 개인 정보 취급 방침
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, privacy information
- WCF, privacy information
- privacy information [WCF]
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
ms.openlocfilehash: e278b28e5c0015eeab549b04d3870dfa247a57ed
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="windows-communication-foundation-privacy-information"></a><span data-ttu-id="a3dd3-102">Windows Communication Foundation 개인 정보 취급 방침</span><span class="sxs-lookup"><span data-stu-id="a3dd3-102">Windows Communication Foundation Privacy Information</span></span>
<span data-ttu-id="a3dd3-103">Microsoft는 최종 사용자의 개인 정보 보호를 위해 최선을 다할 것을 약속합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-103">Microsoft is committed to protecting end-users' privacy.</span></span> <span data-ttu-id="a3dd3-104">Windows Communication Foundation (WCF), 버전 3.0 사용 하 여 응용 프로그램을 빌드할 때 응용 프로그램에 최종 사용자의 개인 정보를 떨어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-104">When you build an application using Windows Communication Foundation (WCF), version 3.0, your application may impact your end-users' privacy.</span></span> <span data-ttu-id="a3dd3-105">예를 들어 응용 프로그램에서 사용자 연락처 정보를 명시적으로 수집하거나, 정보를 요청하거나 인터넷을 통해 정보를 웹 사이트로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-105">For example, your application may explicitly collect user contact information, or it may request or send information over the Internet to your Web site.</span></span> <span data-ttu-id="a3dd3-106">응용 프로그램에 Microsoft 기술을 포함하는 경우 해당 기술의 동작이 개인 정보 보호에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-106">If you embed Microsoft technology in your application, that technology may have its own behavior that might affect privacy.</span></span> <span data-ttu-id="a3dd3-107">WCF 보내지 않습니다 한 정보를 Microsoft 응용 프로그램에서 사용자 또는 최종 사용자를 보낼 하도록 선택 하지 않으면.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-107">WCF does not send any information to Microsoft from your application unless you or the end-user choose to send it to us.</span></span>  
  
## <a name="wcf-in-brief"></a><span data-ttu-id="a3dd3-108">WCF에 대한 간략한 설명</span><span class="sxs-lookup"><span data-stu-id="a3dd3-108">WCF in Brief</span></span>  
 <span data-ttu-id="a3dd3-109">WCF는 개발자가 분산된 응용 프로그램을 빌드할 수 있는 Microsoft.NET Framework를 사용 하 여 분산된 메시징 프레임 워크입니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-109">WCF is a distributed messaging framework using the Microsoft .NET Framework that allows developers to build distributed applications.</span></span> <span data-ttu-id="a3dd3-110">두 응용 프로그램 간에 전달된 메시지에는 헤더 및 본문 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-110">Messages communicated between two applications contain header and body information.</span></span>  
  
 <span data-ttu-id="a3dd3-111">응용 프로그램에서 사용하는 서비스에 따라 헤더에는 메시지 라우팅, 보안 정보, 트랜잭션 등이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-111">Headers may contain message routing, security information, transactions, and more depending on the services used by the application.</span></span> <span data-ttu-id="a3dd3-112">기본적으로 메시지는 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-112">Messages are typically encrypted by default.</span></span> <span data-ttu-id="a3dd3-113">단, 비보안 레거시 웹 서비스에 사용하도록 디자인된 `BasicHttpBinding`을 사용하는 경우는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-113">The one exception is when using the `BasicHttpBinding`, which was designed for use with non-secured, legacy Web services.</span></span> <span data-ttu-id="a3dd3-114">최종 디자인의 책임은 응용 프로그램 디자이너에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-114">As the application designer, you are responsible for the final design.</span></span> <span data-ttu-id="a3dd3-115">SOAP 본문의 메시지에에서 응용 프로그램 관련 데이터 포함 그러나 WCF 암호화 또는 기밀성 기능을 사용 하 여 응용 프로그램 정의 된 개인 정보 같은이 데이터를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-115">Messages in the SOAP body contain application-specific data; however, this data, such as application-defined personal information, can be secured by using WCF encryption or confidentiality features.</span></span> <span data-ttu-id="a3dd3-116">다음 단원에서는 개인 정보 보호에 영향을 주는 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-116">The following sections describe the features that potentially impact privacy.</span></span>  
  
## <a name="messaging"></a><span data-ttu-id="a3dd3-117">메시징</span><span class="sxs-lookup"><span data-stu-id="a3dd3-117">Messaging</span></span>  
 <span data-ttu-id="a3dd3-118">각 WCF 메시지에는 메시지 대상을 지정 하는 주소 헤더를 회신 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-118">Each WCF message has an address header that specifies the message destination and where the reply should go.</span></span>  
  
 <span data-ttu-id="a3dd3-119">끝점 주소의 주소 구성 요소는 끝점을 식별하는 URI(Uniform Resource Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-119">The address component of an endpoint address is a Uniform Resource Identifier (URI) that identifies the endpoint.</span></span> <span data-ttu-id="a3dd3-120">주소는 네트워크 주소나 논리 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-120">The address can be a network address or a logical address.</span></span> <span data-ttu-id="a3dd3-121">주소에는 컴퓨터 이름(호스트 이름, 정규화된 도메인 이름) 및 IP 주소가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-121">The address may include machine name (hostname, fully qualified domain name) and an IP address.</span></span> <span data-ttu-id="a3dd3-122">끝점 주소에는 각 주소를 구분하는 데 사용되는 임시 주소 지정을 위한 GUID(고유한 전역 식별자) 또는 GUID 컬렉션이 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-122">The endpoint address may also contain a globally unique identifier (GUID), or a collection of GUIDs for temporary addressing used to discern each address.</span></span> <span data-ttu-id="a3dd3-123">각 메시지에는 GUID인 메시지 ID가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-123">Each message contains a message ID that is a GUID.</span></span> <span data-ttu-id="a3dd3-124">이 기능은 WS-Addressing 참조 표준을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-124">This feature follows the WS-Addressing reference standard.</span></span>  
  
 <span data-ttu-id="a3dd3-125">WCF 메시징 계층 로컬 컴퓨터에 개인 정보를 쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-125">The WCF messaging layer does not write any personal information to the local machine.</span></span> <span data-ttu-id="a3dd3-126">그러나 끝점 이름에 개인 이름을 사용하거나 끝점의 웹 서비스 기술 언어에 개인 정보를 포함하지만 클라이언트에 https를 사용하여 WSDL에 액세스하도록 요구하지 않는 경우 등 서비스 개발자가 이러한 정보를 노출하는 서비스를 만든 경우 네트워크 수준에서 개인 정보를 전파할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-126">However, it might propagate personal information at the network level if a service developer has created a service that exposes such information (for example, by using a person's name in an endpoint name, or including personal information in the endpoint's Web Services Description Language but not requiring clients to use https to access the WSDL).</span></span> <span data-ttu-id="a3dd3-127">또한 개발자가 실행 되는 경우는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 개인 정보를 해당 출력을 노출 하는 끝점에 대해 도구 해당 정보를 포함 하 고 출력 파일에 기록 됩니다는 로컬 하드 디스크입니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-127">Also, if a developer runs the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool against an endpoint that exposes personal information, the tool's output could contain that information, and the output file is written to the local hard disk.</span></span>  
  
## <a name="hosting"></a><span data-ttu-id="a3dd3-128">호스팅</span><span class="sxs-lookup"><span data-stu-id="a3dd3-128">Hosting</span></span>  
 <span data-ttu-id="a3dd3-129">WCF에서의 호스팅 기능에는 응용 프로그램을을 필요에 따라 시작 하거나 여러 응용 프로그램 간에 포트 공유를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-129">The hosting feature in WCF allows applications to start on demand or to enable port sharing between multiple applications.</span></span> <span data-ttu-id="a3dd3-130">WCF 응용 프로그램에서 인터넷 정보 서비스 (IIS), 비슷합니다 호스팅될 수 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-130">An WCF application can be hosted in Internet Information Services (IIS), similar to [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].</span></span>  
  
 <span data-ttu-id="a3dd3-131">호스팅은 네트워크에 특정 정보를 노출하지 않으며 컴퓨터에 데이터를 보관하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-131">Hosting does not expose any specific information on the network and it does not keep data on the machine.</span></span>  
  
## <a name="message-security"></a><span data-ttu-id="a3dd3-132">메시지 보안</span><span class="sxs-lookup"><span data-stu-id="a3dd3-132">Message Security</span></span>  
 <span data-ttu-id="a3dd3-133">WCF 보안 메시징 응용 프로그램에 대 한 보안 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-133">WCF security provides the security capabilities for messaging applications.</span></span> <span data-ttu-id="a3dd3-134">제공된 보안 기능에는 인증과 권한 부여가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-134">The security functions provided include authentication and authorization.</span></span>  
  
 <span data-ttu-id="a3dd3-135">인증은 클라이언트와 서비스 간에 자격 증명을 전달하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-135">Authentication is performed by passing credentials between the clients and services.</span></span> <span data-ttu-id="a3dd3-136">다음과 같이 전송 수준 보안이나 SOAP 메시지 수준 보안을 통해 인증을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-136">Authentication can be either through transport-level security or through SOAP message-level security, as follows:</span></span>  
  
-   <span data-ttu-id="a3dd3-137">SOAP 메시지 보안에서는 사용자 이름/암호, X.509 인증서, Kerberos 티켓 및 SAML 토큰 같은 자격 증명을 통해 인증이 수행됩니다. 이러한 모든 자격 증명에는 발급자에 따라 개인 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-137">In SOAP message security, authentication is performed through credentials like username/passwords, X.509 certificates, Kerberos tickets, and SAML tokens, all of which might contain personal information, depending on the issuer.</span></span>  
  
-   <span data-ttu-id="a3dd3-138">전송 보안을 사용하는 경우 HTTP 인증 체계(기본, 다이제스트, 협상, Negotiate, Windows 통합 인증, NTLM, 없음 및 익명) 같은 일반적인 전송 인증 메커니즘과 폼 인증을 통해 인증이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-138">Using transport security, authentication is done through traditional transport authentication mechanisms like HTTP authentication schemes (Basic, Digest, Negotiate, Integrated Windows Authorization, NTLM, None, and Anonymous), and form authentication.</span></span>  
  
 <span data-ttu-id="a3dd3-139">인증을 통해 통신하는 끝점 간에 보안 세션이 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-139">Authentication can result in a secure session established between the communicating endpoints.</span></span> <span data-ttu-id="a3dd3-140">세션은 보안 세션의 수명 동안 지속되는 GUID로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-140">The session is identified by a GUID that lasts the lifetime of the security session.</span></span> <span data-ttu-id="a3dd3-141">다음 표에서는 보관되는 데이터와 위치를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-141">The following table shows what is kept and where.</span></span>  
  
|<span data-ttu-id="a3dd3-142">데이터</span><span class="sxs-lookup"><span data-stu-id="a3dd3-142">Data</span></span>|<span data-ttu-id="a3dd3-143">저장소</span><span class="sxs-lookup"><span data-stu-id="a3dd3-143">Storage</span></span>|  
|----------|-------------|  
|<span data-ttu-id="a3dd3-144">사용자 이름, X.509 인증서, Kerberos 토큰, 자격 증명에 대한 참조 등의 프레젠테이션 자격 증명</span><span class="sxs-lookup"><span data-stu-id="a3dd3-144">Presentation credentials, such as username, X.509 certificates, Kerberos tokens, and references to credentials.</span></span>|<span data-ttu-id="a3dd3-145">Windows 인증서 저장소 등의 표준 Windows 자격 증명 관리 메커니즘</span><span class="sxs-lookup"><span data-stu-id="a3dd3-145">Standard Windows credential management mechanisms such as the Windows certificate store.</span></span>|  
|<span data-ttu-id="a3dd3-146">사용자 이름, 암호 등의 사용자 멤버 자격 정보</span><span class="sxs-lookup"><span data-stu-id="a3dd3-146">User membership information, such as usernames and passwords.</span></span>|[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]<span data-ttu-id="a3dd3-147"> 멤버 자격 공급자</span><span class="sxs-lookup"><span data-stu-id="a3dd3-147"> membership providers.</span></span>|  
|<span data-ttu-id="a3dd3-148">서비스를 클라이언트에 인증하는 데 사용되는 서비스에 대한 ID 정보</span><span class="sxs-lookup"><span data-stu-id="a3dd3-148">Identity information about the service used to authenticate the service to clients.</span></span>|<span data-ttu-id="a3dd3-149">서비스의 끝점 주소</span><span class="sxs-lookup"><span data-stu-id="a3dd3-149">Endpoint address of the service.</span></span>|  
|<span data-ttu-id="a3dd3-150">호출자 정보</span><span class="sxs-lookup"><span data-stu-id="a3dd3-150">Caller information.</span></span>|<span data-ttu-id="a3dd3-151">감사 로그</span><span class="sxs-lookup"><span data-stu-id="a3dd3-151">Auditing logs.</span></span>|  
  
## <a name="auditing"></a><span data-ttu-id="a3dd3-152">감사</span><span class="sxs-lookup"><span data-stu-id="a3dd3-152">Auditing</span></span>  
 <span data-ttu-id="a3dd3-153">감사는 인증 및 권한 부여 이벤트의 성공과 실패를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-153">Auditing records the success and failure of authentication and authorization events.</span></span> <span data-ttu-id="a3dd3-154">감사 레코드에는 서비스 URI, 작업 URI, 호출자 ID 등의 데이터가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-154">Auditing records contain the following data: service URI, action URI, and the caller's identification.</span></span>  
  
 <span data-ttu-id="a3dd3-155">또한 감사는 메시지 로깅에서 응용 프로그램별 데이터를 헤더와 본문에 기록할 수 있으므로 관리자가 설정 또는 해제하여 메시지 로깅의 구성을 수정하는 시기를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-155">Auditing also records when the administrator modifies the configuration of message logging (turning it on or off), because message logging may log application-specific data in headers and bodies.</span></span> <span data-ttu-id="a3dd3-156">[!INCLUDE[wxp](../../../includes/wxp-md.md)]의 경우 응용 프로그램 이벤트 로그에 레코드가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-156">For [!INCLUDE[wxp](../../../includes/wxp-md.md)], a record is logged in the application event log.</span></span> <span data-ttu-id="a3dd3-157">[!INCLUDE[wv](../../../includes/wv-md.md)] 및 [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]의 경우 보안 이벤트 로그에 레코드가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-157">For [!INCLUDE[wv](../../../includes/wv-md.md)] and [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], a record is logged in the security event log.</span></span>  
  
## <a name="transactions"></a><span data-ttu-id="a3dd3-158">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="a3dd3-158">Transactions</span></span>  
 <span data-ttu-id="a3dd3-159">트랜잭션 기능은 트랜잭션 서비스를 WCF 응용 프로그램을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-159">The transactions feature provides transactional services to a WCF application.</span></span>  
  
 <span data-ttu-id="a3dd3-160">트랜잭션 전파에 사용된 트랜잭션 헤더에는 GUID인 트랜잭션 ID 또는 인리스트먼트 ID가 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-160">Transaction headers used in transaction propagation may contain Transaction IDs or Enlistment IDs, which are GUIDs.</span></span>  
  
 <span data-ttu-id="a3dd3-161">트랜잭션 기능은 MSDTC(Microsoft Distributed Transaction Coordinator) 트랜잭션 관리자(Windows 구성 요소)를 사용하여 트랜잭션 상태를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-161">The Transactions feature uses the Microsoft Distributed Transaction Coordinator (MSDTC) Transaction Manager (a Windows component) to manage transaction state.</span></span> <span data-ttu-id="a3dd3-162">트랜잭션 관리자 간의 통신은 기본적으로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-162">By default, communications between Transactions Managers are encrypted.</span></span> <span data-ttu-id="a3dd3-163">트랜잭션 관리자는 끝점 참조, 트랜잭션 ID 및 인리스트먼트 ID를 지속적 상태의 일부로 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-163">Transaction Managers may log endpoint references, Transaction IDs, and Enlistment IDs as part of their durable state.</span></span> <span data-ttu-id="a3dd3-164">이 상태의 수명은 트랜잭션 관리자의 로그 파일 수명에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-164">The lifetime of this state is determined by the lifetime of the Transaction Manager’s log file.</span></span> <span data-ttu-id="a3dd3-165">MSDTC 서비스는 이 로그를 소유하고 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-165">The MSDTC service owns and maintains this log.</span></span>  
  
 <span data-ttu-id="a3dd3-166">트랜잭션 기능은 WS-Coordination 및 WS-Atomic Transaction 표준을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-166">The Transactions feature implements the WS-Coordination and WS-Atomic Transaction standards.</span></span>  
  
## <a name="reliable-sessions"></a><span data-ttu-id="a3dd3-167">신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="a3dd3-167">Reliable Sessions</span></span>  
 <span data-ttu-id="a3dd3-168">WCF에서 신뢰할 수 있는 세션 전송 또는 중간 오류가 발생할 때 메시지의 전송 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-168">Reliable sessions in WCF provide the transfer of messages when transport or intermediary failures occur.</span></span> <span data-ttu-id="a3dd3-169">내부 전송에서 연결이 끊어지거나(예: 무선 네트워크의 TCP 연결) 메시지가 손실되는 경우(HTTP 프록시에서 보내는 메시지 또는 들어오는 메시지 삭제)에도 정확히 한 번만 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-169">They provide an exactly-once transfer of messages even when the underlying transport disconnects (for example, a TCP connection on a wireless network) or loses a message (an HTTP proxy dropping an outgoing or incoming message).</span></span> <span data-ttu-id="a3dd3-170">또한 신뢰할 수 있는 세션은 다중 경로 라우팅의 경우와 같이 메시지가 전송된 순서를 유지하여 메시지 다시 정렬을 복구합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-170">Reliable sessions also recover message reordering (as may happen in the case of multipath routing), preserving the order in which the messages were sent.</span></span>  
  
 <span data-ttu-id="a3dd3-171">신뢰할 수 있는 세션은 WS-RM(WS-ReliableMessaging) 프로토콜을 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-171">Reliable sessions are implemented using the WS-ReliableMessaging (WS-RM) protocol.</span></span> <span data-ttu-id="a3dd3-172">신뢰할 수 있는 특정 세션과 연결된 모든 메시지 식별에 사용되는 세션 정보가 들어 있는 WS-RM 헤더를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-172">They add WS-RM headers that contain session information, which is used to identify all messages associated with a particular reliable session.</span></span> <span data-ttu-id="a3dd3-173">각 WS-RM 세션에는 GUID인 식별자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-173">Each WS-RM session has an identifier, which is a GUID.</span></span>  
  
 <span data-ttu-id="a3dd3-174">최종 사용자의 컴퓨터에는 개인 정보가 보관되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-174">No personal information is retained on the end-user's machine.</span></span>  
  
## <a name="queued-channels"></a><span data-ttu-id="a3dd3-175">대기 중인 채널</span><span class="sxs-lookup"><span data-stu-id="a3dd3-175">Queued Channels</span></span>  
 <span data-ttu-id="a3dd3-176">큐는 수신 응용 프로그램을 대신하여 송신 응용 프로그램의 메시지를 저장하고 나중에 이 메시지를 수신 응용 프로그램에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-176">Queues store messages from a sending application on behalf of a receiving application and later forward these messages to the receiving application.</span></span> <span data-ttu-id="a3dd3-177">예를 들어 큐는 수신 응용 프로그램이 임시일 때 송신 응용 프로그램에서 수신 응용 프로그램으로 메시지가 전송되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-177">They help ensure the transfer of messages from sending applications to receiving applications when, for example, the receiving application is transient.</span></span> <span data-ttu-id="a3dd3-178">WCF를 전송으로 Microsoft 메시지 큐 (MSMQ)를 사용 하 여 큐에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-178">WCF provides support for queuing by using Microsoft Message Queuing (MSMQ) as a transport.</span></span>  
  
 <span data-ttu-id="a3dd3-179">대기 중인 채널 기능은 메시지에 헤더를 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-179">The queued channels feature does not add headers to a message.</span></span> <span data-ttu-id="a3dd3-180">대신 적절한 메시지 큐 메시지 속성이 설정된 메시지 큐 메시지를 만들고 메시지 큐 메서드를 호출하여 메시지를 메시지 큐의 큐에 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-180">Instead it creates a Message Queuing message with appropriate Message Queuing message properties set, and invokes Message Queuing methods to put the message in the Message Queuing queue.</span></span> <span data-ttu-id="a3dd3-181">메시지 큐는 Windows에 포함된 선택적 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-181">Message Queuing is an optional component that ships with Windows.</span></span>  
  
 <span data-ttu-id="a3dd3-182">대기 중인 채널 기능은 메시지 큐를 큐 인프라로 사용하므로 최종 사용자의 컴퓨터에 정보를 보관하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-182">No information is retained on the end-user's machine by the queued channels feature, because it uses Message Queuing as the queuing infrastructure.</span></span>  
  
## <a name="com-integration"></a><span data-ttu-id="a3dd3-183">COM+ 통합</span><span class="sxs-lookup"><span data-stu-id="a3dd3-183">COM+ Integration</span></span>  
 <span data-ttu-id="a3dd3-184">이 기능은 기존의 COM 및 COM + 기능을 WCF services와 호환 되는 서비스를 만들 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-184">This feature wraps existing COM and COM+ functionality to create services that are compatible with WCF services.</span></span> <span data-ttu-id="a3dd3-185">이 기능은 특정 헤더를 사용하지 않으며 최종 사용자의 컴퓨터에 데이터를 보관하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-185">This feature does not use specific headers and it does not retain data on the end-user's machine.</span></span>  
  
## <a name="com-service-moniker"></a><span data-ttu-id="a3dd3-186">COM 서비스 모니커</span><span class="sxs-lookup"><span data-stu-id="a3dd3-186">COM Service Moniker</span></span>  
 <span data-ttu-id="a3dd3-187">이 표준 WCF 클라이언트를 관리 되지 않는 래퍼를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-187">This provides an unmanaged wrapper to a standard WCF client.</span></span> <span data-ttu-id="a3dd3-188">이 기능은 통신 중에 특정 헤더를 사용하지 않으며 최종 사용자의 컴퓨터에 데이터를 보관하지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-188">This feature does not have specific headers on the wire nor does it persist data on the machine.</span></span>  
  
## <a name="peer-channel"></a><span data-ttu-id="a3dd3-189">피어 채널</span><span class="sxs-lookup"><span data-stu-id="a3dd3-189">Peer Channel</span></span>  
 <span data-ttu-id="a3dd3-190">피어 채널에는 WCF를 사용 하 여 여러 상대방과 응용 프로그램을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-190">A peer channel enables development of multiparty applications using WCF.</span></span> <span data-ttu-id="a3dd3-191">다중 상대방 메시징은 메시 컨텍스트에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-191">Multiparty messaging occurs in the context of a mesh.</span></span> <span data-ttu-id="a3dd3-192">노드가 참여할 수 있는 메시는 이름으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-192">Meshes are identified by a name that nodes can join.</span></span> <span data-ttu-id="a3dd3-193">피어 채널의 각 노드는 사용자 지정 포트에 TCP 수신기를 만들고 메시의 다른 노드와 연결을 설정하여 복원력을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-193">Each node in the peer channel creates a TCP listener at a user-specified port and establishes connections with other nodes in the mesh to ensure resiliency.</span></span> <span data-ttu-id="a3dd3-194">메시의 다른 노드에 연결하기 위해 노드는 수신기 주소와 컴퓨터의 IP 주소를 비롯한 일부 데이터도 메시의 다른 노드와 교환합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-194">To connect to other nodes in the mesh, nodes also exchange some data, including the listener address and the machine's IP addresses, with other nodes in the mesh.</span></span> <span data-ttu-id="a3dd3-195">메시에서 전송되는 메시지에는 메시지 스푸핑과 변조를 방지하기 위해 보낸 사람과 관련된 보안 정보가 들어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-195">Messages sent around in the mesh can contain security information that pertains to the sender to prevent message spoofing and tampering.</span></span>  
  
 <span data-ttu-id="a3dd3-196">최종 사용자의 컴퓨터에는 개인 정보가 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-196">No personal information is stored on the end-user's machine.</span></span>  
  
## <a name="it-professional-experience"></a><span data-ttu-id="a3dd3-197">IT 전문가 경험</span><span class="sxs-lookup"><span data-stu-id="a3dd3-197">IT Professional Experience</span></span>  
  
### <a name="tracing"></a><span data-ttu-id="a3dd3-198">추적</span><span class="sxs-lookup"><span data-stu-id="a3dd3-198">Tracing</span></span>  
 <span data-ttu-id="a3dd3-199">WCF 인프라의 진단 기능은 전송 및 서비스 모델 계층을 활동 및 이러한 메시지와 관련 된 이벤트를 통해 전달 되는 메시지를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-199">The diagnostics feature of the WCF infrastructure logs messages that pass through the transport and service model layers, and the activities and events associated with these messages.</span></span> <span data-ttu-id="a3dd3-200">이 기능은 기본적으로 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-200">This feature is turned off by default.</span></span> <span data-ttu-id="a3dd3-201">응용 프로그램의 구성 파일을 사용 하 여 사용 여부와 런타임 시 WCF WMI 공급자를 사용 하 여 추적 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-201">It is enabled using the application’s configuration file and the tracing behavior may be modified using the WCF WMI provider at run time.</span></span> <span data-ttu-id="a3dd3-202">활성화되면 추적 인프라는 메시지, 동작 및 처리 이벤트가 포함된 진단 추적을 구성된 수신기로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-202">When enabled, the tracing infrastructure emits a diagnostic trace that contains messages, activities, and processing events to configured listeners.</span></span> <span data-ttu-id="a3dd3-203">출력 형식과 위치는 관리자가 선택한 수신기 구성에 의해 결정되지만 일반적으로 XML 형식 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-203">The format and location of the output are determined by the administrator’s listener configuration choices, but is typically an XML formatted file.</span></span> <span data-ttu-id="a3dd3-204">관리자는 추적 파일에 대해 ACL(액세스 제어 목록)을 설정하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-204">The administrator is responsible for setting the access control list (ACL) on the trace files.</span></span> <span data-ttu-id="a3dd3-205">특히 WAS(Windows Activation System)에서 호스트할 때 관리자는 원하지 않을 경우 공용 가상 루트 디렉터리에서 파일이 제공되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-205">In particular, when hosted by Windows Activation System (WAS), the administrator should make sure the files are not served from the public virtual root directory if that is not desired.</span></span>  
  
 <span data-ttu-id="a3dd3-206">메시지 로깅과 서비스 모델 진단 추적의 두 가지 추적 형식이 있으며, 이에 대해서는 다음 단원에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-206">There are two types of tracing: Message logging and Service Model diagnostic tracing, described in the following section.</span></span> <span data-ttu-id="a3dd3-207">각 형식은 해당 추적 소스인 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> 및 <xref:System.ServiceModel>을 통해 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-207">Each type is configured through its own trace source: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> and <xref:System.ServiceModel>.</span></span> <span data-ttu-id="a3dd3-208">이러한 로깅 추적 소스는 모두 응용 프로그램의 로컬 데이터를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-208">Both of these logging trace sources capture data that is local to the application.</span></span>  
  
### <a name="message-logging"></a><span data-ttu-id="a3dd3-209">메시지 로깅</span><span class="sxs-lookup"><span data-stu-id="a3dd3-209">Message Logging</span></span>  
 <span data-ttu-id="a3dd3-210">메시지 로깅 추적 소스(<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>)를 사용하면 관리자가 시스템을 통과하는 메시지를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-210">The message logging trace source (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) allows an administrator to log the messages that flow through the system.</span></span> <span data-ttu-id="a3dd3-211">구성을 통해 사용자는 전체 메시지 또는 메시지 헤더만 기록할지, 전송 및/또는 서비스 모델 계층에 기록할지 여부 및 잘못된 형식의 메시지를 포함할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-211">Through configuration, the user may decide to log entire messages or message headers only, whether to log at the transport and/or service model layers, and whether to include malformed messages.</span></span> <span data-ttu-id="a3dd3-212">또한 사용자는 필터링을 구성하여 기록할 메시지를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-212">Also, the user may configure filtering to restrict which messages are logged.</span></span>  
  
 <span data-ttu-id="a3dd3-213">기본적으로 메시지 로깅은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-213">By default, message logging is disabled.</span></span> <span data-ttu-id="a3dd3-214">로컬 컴퓨터 관리자는 응용 프로그램 수준 관리자가 메시지 로깅을 설정하지 않도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-214">The local machine administrator can prevent the application-level administrator from turning message logging on.</span></span>  
  
#### <a name="encrypted-and-decrypted-message-logging"></a><span data-ttu-id="a3dd3-215">암호화 및 해독된 메시지 로깅</span><span class="sxs-lookup"><span data-stu-id="a3dd3-215">Encrypted and Decrypted Message Logging</span></span>  
 <span data-ttu-id="a3dd3-216">메시지는 다음 용어에 설명된 대로 기록, 암호화 또는 해독됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-216">Messages are logged, encrypted, or decrypted, as described in the following terms.</span></span>  
  
 <span data-ttu-id="a3dd3-217">전송 로깅</span><span class="sxs-lookup"><span data-stu-id="a3dd3-217">Transport Logging</span></span>  
 <span data-ttu-id="a3dd3-218">전송 수준에서 수신 및 전송된 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-218">Logs messages received and sent at the transport level.</span></span> <span data-ttu-id="a3dd3-219">이 메시지에는 모든 헤더가 들어 있으며, 통신 중에 전송하기 전과 수신할 때 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-219">These messages contain all headers, and may be encrypted before being sent on the wire and when being received.</span></span>  
  
 <span data-ttu-id="a3dd3-220">통신 중에 전송하기 전과 수신할 때 메시지가 암호화되는 경우 암호화된 상태로도 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-220">If messages are encrypted before being sent on the wire and when they are received, they are logged encrypted as well.</span></span> <span data-ttu-id="a3dd3-221">단, 보안 프로토콜(https)을 사용하는 경우는 예외입니다. 메시지가 통신 중에 암호화되는 경우에도 전송되기 전과 수신된 후 해독되어 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-221">An exception is when a security protocol is used (https): they are then logged decrypted before being sent and after being received even if they are encrypted on the wire.</span></span>  
  
 <span data-ttu-id="a3dd3-222">서비스 로깅</span><span class="sxs-lookup"><span data-stu-id="a3dd3-222">Service Logging</span></span>  
 <span data-ttu-id="a3dd3-223">채널 헤더 처리가 발생한 후, 사용자 코드를 입력하기 직전과 그 후에 서비스 모델 수준에서 수신 또는 전송된 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-223">Logs messages received or sent at the service model level, after channel header processing has occurred, just before and after entering user code.</span></span>  
  
 <span data-ttu-id="a3dd3-224">이 수준에서 기록된 메시지는 통신 중에 보안 및 암호화된 경우에도 해독됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-224">Messages logged at this level are decrypted even if they were secured and encrypted on the wire.</span></span>  
  
 <span data-ttu-id="a3dd3-225">잘못된 형식의 메시지 로깅</span><span class="sxs-lookup"><span data-stu-id="a3dd3-225">Malformed Message Logging</span></span>  
 <span data-ttu-id="a3dd3-226">WCF 인프라에서 이해할 수 없거나 처리할 메시지를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-226">Logs messages that the WCF infrastructure cannot understand or process.</span></span>  
  
 <span data-ttu-id="a3dd3-227">메시지는 있는 그대로, 즉 암호화된 상태나 암호화되지 않은 상태로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-227">Messages are logged as-is, that is, encrypted or not</span></span>  
  
 <span data-ttu-id="a3dd3-228">메시지 기록 될 때 암호 해독 / 암호화 되지 않은 형태로 기본적으로 WCF 제거 보안 키와 잠재적 개인 정보 메시지를 기록 하기 전에.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-228">When messages are logged in decrypted or unencrypted form, by default WCF removes security keys and potentially personal information from the messages before logging them.</span></span> <span data-ttu-id="a3dd3-229">다음 단원에서는 제거되는 정보와 시기에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-229">The next sections describe what information is removed, and when.</span></span> <span data-ttu-id="a3dd3-230">키와 잠재적 개인 정보를 기록하려면 컴퓨터 관리자와 응용 프로그램 배포자가 모두 특정 구성 작업을 수행하여 기본 동작을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-230">The machine administrator and application deployer must both take certain configuration actions to change the default behavior to log keys and potentially personal information.</span></span>  
  
#### <a name="information-removed-from-message-headers-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="a3dd3-231">해독/암호화되지 않은 메시지를 기록할 때 메시지 헤더에서 제거되는 정보</span><span class="sxs-lookup"><span data-stu-id="a3dd3-231">Information Removed from Message Headers When Logging Decrypted/Unencrypted Messages</span></span>  
 <span data-ttu-id="a3dd3-232">메시지가 해독/암호화되지 않은 형태로 기록되는 경우 기본적으로 메시지를 기록하기 전에 보안 키와 잠재적 개인 정보가 메시지 헤더와 메시지 본문에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-232">When messages are logged in decrypted/unencrypted form, security keys and potentially personal information are removed by default from message headers and message bodies before they are logged.</span></span> <span data-ttu-id="a3dd3-233">다음은 WCF 키와 잠재적 개인 정보 고려 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-233">The following list shows what WCF considers keys and potentially personal information.</span></span>  
  
 <span data-ttu-id="a3dd3-234">제거되는 키</span><span class="sxs-lookup"><span data-stu-id="a3dd3-234">Keys that are removed:</span></span>  
  
 <span data-ttu-id="a3dd3-235">\- Xmlns: wst = "http://schemas.xmlsoap.org/ws/2004/04/trust" 및 xmlns: wst = "http://schemas.xmlsoap.org/ws/2005/02/trust"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-235">\- For xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"</span></span>  
  
 <span data-ttu-id="a3dd3-236">wst:BinarySecret</span><span class="sxs-lookup"><span data-stu-id="a3dd3-236">wst:BinarySecret</span></span>  
  
 <span data-ttu-id="a3dd3-237">wst:Entropy</span><span class="sxs-lookup"><span data-stu-id="a3dd3-237">wst:Entropy</span></span>  
  
 <span data-ttu-id="a3dd3-238">\- Xmlns:wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" 및 xmlns:wsse = "http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-238">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="a3dd3-239">wsse:Password</span><span class="sxs-lookup"><span data-stu-id="a3dd3-239">wsse:Password</span></span>  
  
 <span data-ttu-id="a3dd3-240">wsse:Nonce</span><span class="sxs-lookup"><span data-stu-id="a3dd3-240">wsse:Nonce</span></span>  
  
 <span data-ttu-id="a3dd3-241">제거되는 잠재적 개인 정보</span><span class="sxs-lookup"><span data-stu-id="a3dd3-241">Potentially personal information that is removed:</span></span>  
  
 <span data-ttu-id="a3dd3-242">\- Xmlns:wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" 및 xmlns:wsse = "http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-242">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="a3dd3-243">wsse:Username</span><span class="sxs-lookup"><span data-stu-id="a3dd3-243">wsse:Username</span></span>  
  
 <span data-ttu-id="a3dd3-244">wsse:BinarySecurityToken</span><span class="sxs-lookup"><span data-stu-id="a3dd3-244">wsse:BinarySecurityToken</span></span>  
  
 <span data-ttu-id="a3dd3-245">\- Xmlns: saml = "urn: oasis: 이름: tc: SAML:1.0:assertion" 항목 굵게 (아래 참조)이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-245">\- For xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" the items in bold (below) are removed:</span></span>  
  
 <span data-ttu-id="a3dd3-246">\<어설션</span><span class="sxs-lookup"><span data-stu-id="a3dd3-246">\<Assertion</span></span>  
  
 <span data-ttu-id="a3dd3-247">MajorVersion="1"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-247">MajorVersion="1"</span></span>  
  
 <span data-ttu-id="a3dd3-248">MinorVersion="1"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-248">MinorVersion="1"</span></span>  
  
 <span data-ttu-id="a3dd3-249">AssertionId="[ID]"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-249">AssertionId="[ID]"</span></span>  
  
 <span data-ttu-id="a3dd3-250">Issuer="[string]"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-250">Issuer="[string]"</span></span>  
  
 <span data-ttu-id="a3dd3-251">IssueInstant="[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-251">IssueInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="a3dd3-252">\<Conditions NotBefore="[dateTime]" NotOnOrAfter="[dateTime]"></span><span class="sxs-lookup"><span data-stu-id="a3dd3-252">\<Conditions NotBefore="[dateTime]" NotOnOrAfter="[dateTime]"></span></span>  
  
 <span data-ttu-id="a3dd3-253">\<AudienceRestrictionCondition></span><span class="sxs-lookup"><span data-stu-id="a3dd3-253">\<AudienceRestrictionCondition></span></span>  
  
 <span data-ttu-id="a3dd3-254">\<Audience>[uri]\</Audience>+</span><span class="sxs-lookup"><span data-stu-id="a3dd3-254">\<Audience>[uri]\</Audience>+</span></span>  
  
 <span data-ttu-id="a3dd3-255">\</AudienceRestrictionCondition>\*</span><span class="sxs-lookup"><span data-stu-id="a3dd3-255">\</AudienceRestrictionCondition>\*</span></span>  
  
 <span data-ttu-id="a3dd3-256">\<DoNotCacheCondition />\*</span><span class="sxs-lookup"><span data-stu-id="a3dd3-256">\<DoNotCacheCondition />\*</span></span>  
  
 <span data-ttu-id="a3dd3-257"><\!-기본 형식이 추상</span><span class="sxs-lookup"><span data-stu-id="a3dd3-257"><\!-- abstract base type</span></span>  
  
 <span data-ttu-id="a3dd3-258">\<조건 / > \*</span><span class="sxs-lookup"><span data-stu-id="a3dd3-258">\<Condition />\*</span></span>  
  
 -->  
  
 <span data-ttu-id="a3dd3-259">\</ 조건 >?</span><span class="sxs-lookup"><span data-stu-id="a3dd3-259">\</Conditions>?</span></span>  
  
 <span data-ttu-id="a3dd3-260">\<조언 ></span><span class="sxs-lookup"><span data-stu-id="a3dd3-260">\<Advice></span></span>  
  
 <span data-ttu-id="a3dd3-261">\<AssertionIDReference>[ID]\</AssertionIDReference>\*</span><span class="sxs-lookup"><span data-stu-id="a3dd3-261">\<AssertionIDReference>[ID]\</AssertionIDReference>\*</span></span>  
  
 <span data-ttu-id="a3dd3-262">\<Assertion>[assertion]\</Assertion>\*</span><span class="sxs-lookup"><span data-stu-id="a3dd3-262">\<Assertion>[assertion]\</Assertion>\*</span></span>  
  
 <span data-ttu-id="a3dd3-263">[any]\*</span><span class="sxs-lookup"><span data-stu-id="a3dd3-263">[any]\*</span></span>  
  
 <span data-ttu-id="a3dd3-264">\</ 통지 >?</span><span class="sxs-lookup"><span data-stu-id="a3dd3-264">\</Advice>?</span></span>  
  
 <span data-ttu-id="a3dd3-265"><\!-추상 기본 유형</span><span class="sxs-lookup"><span data-stu-id="a3dd3-265"><\!-- Abstract base types</span></span>  
  
 <span data-ttu-id="a3dd3-266">\<문 / > \*</span><span class="sxs-lookup"><span data-stu-id="a3dd3-266">\<Statement />\*</span></span>  
  
 <span data-ttu-id="a3dd3-267">\<SubjectStatement ></span><span class="sxs-lookup"><span data-stu-id="a3dd3-267">\<SubjectStatement></span></span>  
  
 <span data-ttu-id="a3dd3-268">\<제목 ></span><span class="sxs-lookup"><span data-stu-id="a3dd3-268">\<Subject></span></span>  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 <span data-ttu-id="a3dd3-269">\<SubjectConfirmation ></span><span class="sxs-lookup"><span data-stu-id="a3dd3-269">\<SubjectConfirmation></span></span>  
  
 <span data-ttu-id="a3dd3-270">\<ConfirmationMethod>[anyUri]\</ConfirmationMethod>+</span><span class="sxs-lookup"><span data-stu-id="a3dd3-270">\<ConfirmationMethod>[anyUri]\</ConfirmationMethod>+</span></span>  
  
 <span data-ttu-id="a3dd3-271">\<SubjectConfirmationData>[any]\</SubjectConfirmationData>?</span><span class="sxs-lookup"><span data-stu-id="a3dd3-271">\<SubjectConfirmationData>[any]\</SubjectConfirmationData>?</span></span>  
  
 <span data-ttu-id="a3dd3-272">\<ds:KeyInfo>...\</ds:KeyInfo>?</span><span class="sxs-lookup"><span data-stu-id="a3dd3-272">\<ds:KeyInfo>...\</ds:KeyInfo>?</span></span>  
  
 <span data-ttu-id="a3dd3-273">\</SubjectConfirmation>?</span><span class="sxs-lookup"><span data-stu-id="a3dd3-273">\</SubjectConfirmation>?</span></span>  
  
 <span data-ttu-id="a3dd3-274">\</Subject></span><span class="sxs-lookup"><span data-stu-id="a3dd3-274">\</Subject></span></span>  
  
 <span data-ttu-id="a3dd3-275">\</SubjectStatement>\*</span><span class="sxs-lookup"><span data-stu-id="a3dd3-275">\</SubjectStatement>\*</span></span>  
  
 -->  
  
 <span data-ttu-id="a3dd3-276">\<AuthenticationStatement</span><span class="sxs-lookup"><span data-stu-id="a3dd3-276">\<AuthenticationStatement</span></span>  
  
 <span data-ttu-id="a3dd3-277">AuthenticationMethod="[uri]"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-277">AuthenticationMethod="[uri]"</span></span>  
  
 <span data-ttu-id="a3dd3-278">AuthenticationInstant="[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-278">AuthenticationInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="a3dd3-279">[Subject]</span><span class="sxs-lookup"><span data-stu-id="a3dd3-279">[Subject]</span></span>  
  
 `<SubjectLocality`  
  
 `IPAddress="[string]"?`  
  
 `DNSAddress="[string]"?`  
  
 `/>?`  
  
 <span data-ttu-id="a3dd3-280"><AuthorityBinding</span><span class="sxs-lookup"><span data-stu-id="a3dd3-280"><AuthorityBinding</span></span>  
  
 <span data-ttu-id="a3dd3-281">AuthorityKind="[QName]"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-281">AuthorityKind="[QName]"</span></span>  
  
 <span data-ttu-id="a3dd3-282">Location="[uri]"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-282">Location="[uri]"</span></span>  
  
 <span data-ttu-id="a3dd3-283">Binding="[uri]"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-283">Binding="[uri]"</span></span>  
  
 />*  
  
 <span data-ttu-id="a3dd3-284">\</AuthenticationStatement>\*</span><span class="sxs-lookup"><span data-stu-id="a3dd3-284">\</AuthenticationStatement>\*</span></span>  
  
 <span data-ttu-id="a3dd3-285">\<요소의 AttributeStatement ></span><span class="sxs-lookup"><span data-stu-id="a3dd3-285">\<AttributeStatement></span></span>  
  
 <span data-ttu-id="a3dd3-286">[Subject]</span><span class="sxs-lookup"><span data-stu-id="a3dd3-286">[Subject]</span></span>  
  
 <span data-ttu-id="a3dd3-287">\<특성</span><span class="sxs-lookup"><span data-stu-id="a3dd3-287">\<Attribute</span></span>  
  
 <span data-ttu-id="a3dd3-288">AttributeName="[string]"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-288">AttributeName="[string]"</span></span>  
  
 <span data-ttu-id="a3dd3-289">AttributeNamespace="[uri]"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-289">AttributeNamespace="[uri]"</span></span>  
  
 >  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 <span data-ttu-id="a3dd3-290">\</Attribute>+</span><span class="sxs-lookup"><span data-stu-id="a3dd3-290">\</Attribute>+</span></span>  
  
 <span data-ttu-id="a3dd3-291">\</AttributeStatement>\*</span><span class="sxs-lookup"><span data-stu-id="a3dd3-291">\</AttributeStatement>\*</span></span>  
  
 <span data-ttu-id="a3dd3-292">\<AuthorizationDecisionStatement</span><span class="sxs-lookup"><span data-stu-id="a3dd3-292">\<AuthorizationDecisionStatement</span></span>  
  
 <span data-ttu-id="a3dd3-293">Resource="[uri]"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-293">Resource="[uri]"</span></span>  
  
 <span data-ttu-id="a3dd3-294">Decision="[Permit&#124;Deny&#124;Indeterminate]"</span><span class="sxs-lookup"><span data-stu-id="a3dd3-294">Decision="[Permit&#124;Deny&#124;Indeterminate]"</span></span>  
  
 >  
  
 <span data-ttu-id="a3dd3-295">[Subject]</span><span class="sxs-lookup"><span data-stu-id="a3dd3-295">[Subject]</span></span>  
  
 <span data-ttu-id="a3dd3-296">\<Action Namespace="[uri]">[string]\</Action>+</span><span class="sxs-lookup"><span data-stu-id="a3dd3-296">\<Action Namespace="[uri]">[string]\</Action>+</span></span>  
  
 <span data-ttu-id="a3dd3-297">\<증명 정보 ></span><span class="sxs-lookup"><span data-stu-id="a3dd3-297">\<Evidence></span></span>  
  
 <span data-ttu-id="a3dd3-298">\<AssertionIDReference>[ID]\</AssertionIDReference>+</span><span class="sxs-lookup"><span data-stu-id="a3dd3-298">\<AssertionIDReference>[ID]\</AssertionIDReference>+</span></span>  
  
 <span data-ttu-id="a3dd3-299">\<Assertion>[assertion]\</Assertion>+</span><span class="sxs-lookup"><span data-stu-id="a3dd3-299">\<Assertion>[assertion]\</Assertion>+</span></span>  
  
 <span data-ttu-id="a3dd3-300">\</ 증명 정보 >?</span><span class="sxs-lookup"><span data-stu-id="a3dd3-300">\</Evidence>?</span></span>  
  
 <span data-ttu-id="a3dd3-301">\</AuthorizationDecisionStatement>\*</span><span class="sxs-lookup"><span data-stu-id="a3dd3-301">\</AuthorizationDecisionStatement>\*</span></span>  
  
 <span data-ttu-id="a3dd3-302">\</Assertion></span><span class="sxs-lookup"><span data-stu-id="a3dd3-302">\</Assertion></span></span>  
  
#### <a name="information-removed-from-message-bodies-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="a3dd3-303">해독/암호화되지 않은 메시지를 기록할 때 메시지 본문에서 제거되는 정보</span><span class="sxs-lookup"><span data-stu-id="a3dd3-303">Information Removed from Message Bodies When Logging Decrypted/Unencrypted Messages</span></span>  
 <span data-ttu-id="a3dd3-304">앞에서 설명한 대로, WCF 제거 키와 알려진된 잠재적 개인 정보 기록 된 해독/암호화 되지 않은 메시지에 대 한 메시지 헤더에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-304">As previously described, WCF removes keys and known potentially personal information from message headers for logged decrypted/unencrypted messages.</span></span> <span data-ttu-id="a3dd3-305">또한 WCF의 본문 요소와 다음 목록에 키 교환에 관련 된 보안 메시지를 설명 하는 작업에 대 한 메시지 본문에서 키와 알려진된 잠재적 개인 정보를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-305">In addition, WCF removes keys and known potentially personal information from message bodies for the body elements and actions in the following list, which describe security messages involved in key exchange.</span></span>  
  
 <span data-ttu-id="a3dd3-306">다음 네임스페이스의 경우</span><span class="sxs-lookup"><span data-stu-id="a3dd3-306">For the following namespaces:</span></span>  
  
 <span data-ttu-id="a3dd3-307">xmlns: wst = "http://schemas.xmlsoap.org/ws/2004/04/trust" 및 xmlns: wst = "http://schemas.xmlsoap.org/ws/2005/02/trust" (예를 들어 작업이 없는 경우 사용할 수 있는)</span><span class="sxs-lookup"><span data-stu-id="a3dd3-307">xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" (for example, if no action available)</span></span>  
  
 <span data-ttu-id="a3dd3-308">키 교환과 관련된 다음 본문 요소에서 정보가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-308">Information is removed for these body elements, which involve key exchange:</span></span>  
  
 <span data-ttu-id="a3dd3-309">wst:RequestSecurityToken</span><span class="sxs-lookup"><span data-stu-id="a3dd3-309">wst:RequestSecurityToken</span></span>  
  
 <span data-ttu-id="a3dd3-310">wst:RequestSecurityTokenResponse</span><span class="sxs-lookup"><span data-stu-id="a3dd3-310">wst:RequestSecurityTokenResponse</span></span>  
  
 <span data-ttu-id="a3dd3-311">wst:RequestSecurityTokenResponseCollection</span><span class="sxs-lookup"><span data-stu-id="a3dd3-311">wst:RequestSecurityTokenResponseCollection</span></span>  
  
 <span data-ttu-id="a3dd3-312">다음 각 작업에서도 정보가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-312">Information is also removed for each of the following Actions:</span></span>  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Renew  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Renew  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Cancel  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Cancel  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Validate  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Validate  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Amend  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Amend  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Renew  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Renew  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Cancel  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Cancel  
  
 http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT  
  
 http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT  
  
 http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT-Amend  
  
 http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT-Amend  
  
#### <a name="no-information-is-removed-from-application-specific-headers-and-body-data"></a><span data-ttu-id="a3dd3-313">응용 프로그램별 헤더 및 본문 데이터의 정보는 제거되지 않음</span><span class="sxs-lookup"><span data-stu-id="a3dd3-313">No Information Is Removed from Application-specific Headers and Body Data</span></span>  
 <span data-ttu-id="a3dd3-314">WCF 응용 프로그램별 헤더 (예: 쿼리 문자열) 또는 본문 데이터 (예: 신용 카드 번호)의 개인 정보를 추적 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-314">WCF does not track personal information in application-specific headers (for example, query strings) or body data (for example, credit card number).</span></span>  
  
 <span data-ttu-id="a3dd3-315">메시지 로깅을 설정하면 응용 프로그램별 헤더와 본문 정보의 개인 정보가 로그에 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-315">When message logging is on, personal information in application-specific headers and body information may be visible in the logs.</span></span> <span data-ttu-id="a3dd3-316">응용 프로그램 배포자는 구성 및 로그 파일에 ACL을 설정하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-316">Again, the application deployer is responsible for setting the ACLs on the configuration and log files.</span></span> <span data-ttu-id="a3dd3-317">또한 이 정보를 표시하지 않으려면 로깅을 해제할 수 있으며 이 정보가 기록된 후 로그 파일에서 필터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-317">He also can turn off logging if he does not want this information to be visible, or he may filter out this information from the log files after it is logged.</span></span>  
  
### <a name="service-model-tracing"></a><span data-ttu-id="a3dd3-318">서비스 모델 추적</span><span class="sxs-lookup"><span data-stu-id="a3dd3-318">Service Model Tracing</span></span>  
 <span data-ttu-id="a3dd3-319">서비스 모델 추적 소스(<xref:System.ServiceModel>)는 메시지 처리와 관련된 동작 및 이벤트 추적을 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-319">The Service Model trace source (<xref:System.ServiceModel>) enables tracing of activities and events related to message processing.</span></span> <span data-ttu-id="a3dd3-320">이 기능은 <xref:System.Diagnostics>의 .NET Framework 진단 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-320">This feature uses the .NET Framework diagnostic functionality from <xref:System.Diagnostics>.</span></span> <span data-ttu-id="a3dd3-321"><xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> 속성과 마찬가지로 사용자가 .NET Framework 응용 프로그램 구성 파일을 사용하여 위치와 해당 ACL을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-321">As with the <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> property, the location and its ACL are user-configurable using .NET Framework application configuration files.</span></span> <span data-ttu-id="a3dd3-322">메시지 로깅과 마찬가지로 파일 위치는 항상 관리자가 추적을 활성화할 때 구성되므로 관리자가 ACL을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-322">As with message logging, the file location is always configured when the administrator enables tracing; thus, the administrator controls the ACL.</span></span>  
  
 <span data-ttu-id="a3dd3-323">메시지가 범위 내에 있으면 추적에 메시지 헤더가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-323">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="a3dd3-324">이전 단원에서 메시지 헤더에서 잠재적 개인 정보를 숨기는 경우에 대한 것과 동일한 규칙이 적용됩니다. 기본적으로 이전에 식별된 개인 정보가 추적 중인 헤더에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-324">The same rules for hiding potentially personal information in message headers in the previous section apply: the personal information previously identified is removed by default from the headers in traces.</span></span> <span data-ttu-id="a3dd3-325">잠재적 개인 정보를 기록하려면 컴퓨터 관리자와 응용 프로그램 배포자가 모두 구성을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-325">Both the machine administrator and the application deployer must modify the configuration in order to log potentially personal information.</span></span> <span data-ttu-id="a3dd3-326">그러나 응용 프로그램별 헤더에 포함된 개인 정보는 추적에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-326">However, personal information contained in application-specific headers is logged in traces.</span></span> <span data-ttu-id="a3dd3-327">응용 프로그램 배포자는 구성 및 추적 파일에 ACL을 설정하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-327">The application deployer is responsible for setting the ACLs on the configuration and trace files.</span></span> <span data-ttu-id="a3dd3-328">또한 이 정보를 표시하지 않으려면 추적을 해제할 수 있으며 이 정보가 기록된 후 추적 파일에서 필터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-328">He also can turn off tracing if he does not want this information to be visible, or he can filter out this information from the trace files after it is logged.</span></span>  
  
 <span data-ttu-id="a3dd3-329">ServiceModel 추적의 일부로 고유 ID(동작 ID라고 하며 일반적으로 GUID임)는 메시지가 인프라의 여러 부분을 통과할 때 여러 동작을 함께 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-329">As part of ServiceModel Tracing, Unique IDs (called Activity IDs, and typically a GUID) link different activities together as a message flows through different parts of the infrastructure.</span></span>  
  
#### <a name="custom-trace-listeners"></a><span data-ttu-id="a3dd3-330">사용자 지정 추적 수신기</span><span class="sxs-lookup"><span data-stu-id="a3dd3-330">Custom Trace Listeners</span></span>  
 <span data-ttu-id="a3dd3-331">메시지 로깅 및 추적에 대해 통신 중에 추적과 메시지를 원격 데이터베이스 등에 보낼 수 있는 사용자 지정 추적 수신기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-331">For both message logging and tracing, a custom trace listener can be configured, which can send traces and messages on the wire (for example, to a remote database).</span></span> <span data-ttu-id="a3dd3-332">응용 프로그램 배포자는 사용자 지정 수신기를 구성하거나 사용자가 구성할 수 있게 하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-332">The application deployer is responsible for configuring custom listeners or enabling users to do so.</span></span> <span data-ttu-id="a3dd3-333">또한 원격 위치에 노출되는 모든 개인 정보에 대한 책임이 있으며 이 위치에 ACL을 적절하게 적용하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-333">He is also responsible for any personal information exposed at the remote location, and for properly applying ACLs to this location.</span></span>  
  
### <a name="other-features-for-it-professionals"></a><span data-ttu-id="a3dd3-334">IT 전문가용 기타 기능</span><span class="sxs-lookup"><span data-stu-id="a3dd3-334">Other features for IT Professionals</span></span>  
 <span data-ttu-id="a3dd3-335">WCF는 WMI (Windows와 함께 제공)를 통해 WCF 인프라 구성 정보를 노출 하는 WMI 공급자를 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-335">WCF has a WMI provider that exposes the WCF infrastructure configuration information through WMI (shipped with Windows).</span></span> <span data-ttu-id="a3dd3-336">기본적으로 관리자는 WMI 인터페이스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-336">By default, the WMI interface is available to administrators.</span></span>  
  
 <span data-ttu-id="a3dd3-337">WCF 구성에서는.NET Framework 구성 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-337">WCF configuration uses the .NET Framework configuration mechanism.</span></span> <span data-ttu-id="a3dd3-338">구성 파일은 컴퓨터에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-338">The configuration files are stored on the machine.</span></span> <span data-ttu-id="a3dd3-339">응용 프로그램 개발자와 관리자는 응용 프로그램의 각 요구 사항에 대한 구성 파일과 ACL을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-339">The application developer and the administrator create the configuration files and ACL for each of the application's requirements.</span></span> <span data-ttu-id="a3dd3-340">구성 파일에는 끝점 주소와 인증서 저장소의 인증서에 대한 링크가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-340">A configuration file can contain endpoint addresses and links to certificates in the certificate store.</span></span> <span data-ttu-id="a3dd3-341">인증서는 응용 프로그램에서 사용하는 기능의 다양한 속성을 구성하기 위해 응용 프로그램 데이터를 제공하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-341">The certificates can be used to provide application data to configure various properties of the features used by the application.</span></span>  
  
 <span data-ttu-id="a3dd3-342">호출 하 여 WCF 또한 사용 하 여.NET Framework 프로세스 덤프 기능은 <xref:System.Environment.FailFast%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-342">WCF also uses the .NET Framework process dump functionality by calling the <xref:System.Environment.FailFast%2A> method.</span></span>  
  
### <a name="it-pro-tools"></a><span data-ttu-id="a3dd3-343">IT 전문가 도구</span><span class="sxs-lookup"><span data-stu-id="a3dd3-343">IT Pro Tools</span></span>  
 <span data-ttu-id="a3dd3-344">WCF에는 Windows SDK에서 제공 되는 다음 IT 전문가 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-344">WCF also provides the following IT professional tools, which ship in the Windows SDK.</span></span>  
  
#### <a name="svctraceviewerexe"></a><span data-ttu-id="a3dd3-345">SvcTraceViewer.exe</span><span class="sxs-lookup"><span data-stu-id="a3dd3-345">SvcTraceViewer.exe</span></span>  
 <span data-ttu-id="a3dd3-346">뷰어는 WCF 추적 파일을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-346">The viewer displays WCF trace files.</span></span> <span data-ttu-id="a3dd3-347">뷰어는 추적에 포함된 모든 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-347">The viewer shows whatever information is contained in the traces.</span></span>  
  
#### <a name="svcconfigeditorexe"></a><span data-ttu-id="a3dd3-348">SvcConfigEditor.exe</span><span class="sxs-lookup"><span data-stu-id="a3dd3-348">SvcConfigEditor.exe</span></span>  
 <span data-ttu-id="a3dd3-349">편집기를 만들고 WCF 구성 파일을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-349">The editor allows the user to create and edit WCF configuration files.</span></span> <span data-ttu-id="a3dd3-350">편집기는 구성 파일에 포함된 모든 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-350">The editor shows whatever information is contained in the configuration files.</span></span> <span data-ttu-id="a3dd3-351">텍스트 편집기를 사용하여 동일한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-351">The same task can be accomplished with a text editor.</span></span>  
  
#### <a name="servicemodelreg"></a><span data-ttu-id="a3dd3-352">ServiceModel_Reg</span><span class="sxs-lookup"><span data-stu-id="a3dd3-352">ServiceModel_Reg</span></span>  
 <span data-ttu-id="a3dd3-353">이 도구를 통해 사용자는 컴퓨터의 ServiceModel 설치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-353">This tool allows the user to manage ServiceModel installs on a machine.</span></span> <span data-ttu-id="a3dd3-354">도구에서 실행 되며, 프로세스에서 WCF 설치의 구성에 대 한 정보를 표시할 수 있습니다 때 콘솔 창에 상태 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-354">The tool displays status messages in a console window when it runs and, in the process, may display information about the configuration of the WCF installation.</span></span>  
  
#### <a name="wsatconfigexe-and-wsatuidll"></a><span data-ttu-id="a3dd3-355">WSATConfig.exe 및 WSATUI.dll</span><span class="sxs-lookup"><span data-stu-id="a3dd3-355">WSATConfig.exe and WSATUI.dll</span></span>  
 <span data-ttu-id="a3dd3-356">이러한 도구는 WCF의 상호 운용 가능한 Ws-atomictransaction 네트워크 지원을 구성 하려면 IT 전문가 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-356">These tools allow IT Professionals to configure interoperable WS-AtomicTransaction network support in WCF.</span></span> <span data-ttu-id="a3dd3-357">이 도구는 레지스트리에 저장된 가장 일반적으로 사용되는 WS-AtomicTransaction 설정의 값을 표시하고 사용자가 변경할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-357">The tools display and allow the user to change the values of the most commonly used WS-AtomicTransaction settings stored in the registry.</span></span>  
  
## <a name="cross-cutting-features"></a><span data-ttu-id="a3dd3-358">교차 편집 기능</span><span class="sxs-lookup"><span data-stu-id="a3dd3-358">Cross-cutting Features</span></span>  
 <span data-ttu-id="a3dd3-359">다음 기능은 교차 편집 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-359">The following features are cross-cutting.</span></span> <span data-ttu-id="a3dd3-360">즉, 앞의 기능을 임의로 조합하여 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-360">That is, they can be composed with any of the preceding features.</span></span>  
  
### <a name="service-framework"></a><span data-ttu-id="a3dd3-361">서비스 프레임워크</span><span class="sxs-lookup"><span data-stu-id="a3dd3-361">Service Framework</span></span>  
 <span data-ttu-id="a3dd3-362">메시지를 CLR 클래스의 인스턴스와 연결하는 GUID인 인스턴스 ID가 헤더에 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-362">Headers can contain an instance ID, which is a GUID that associates a message with an instance of a CLR class.</span></span>  
  
 <span data-ttu-id="a3dd3-363">WSDL(웹 서비스 기술 언어)에는 포트 정의가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-363">The Web Services Description Language (WSDL) contains a definition of the port.</span></span> <span data-ttu-id="a3dd3-364">각 포트에는 끝점 주소와 응용 프로그램에서 사용하는 서비스를 나타내는 바인딩이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-364">Each port has an endpoint address and a binding that represents the services used by the application.</span></span> <span data-ttu-id="a3dd3-365">구성을 사용하여 WSDL 노출을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-365">Exposing WSDL can be turned off using configuration.</span></span> <span data-ttu-id="a3dd3-366">컴퓨터에는 정보가 보관되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-366">No information is retained on the machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3dd3-367">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3dd3-367">See Also</span></span>  
 [<span data-ttu-id="a3dd3-368">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="a3dd3-368">Windows Communication Foundation</span></span>](http://msdn.microsoft.com/library/fd327ade-0260-4c40-adbe-b74645ba3277)  
 [<span data-ttu-id="a3dd3-369">보안</span><span class="sxs-lookup"><span data-stu-id="a3dd3-369">Security</span></span>](../../../docs/framework/wcf/feature-details/security.md)
