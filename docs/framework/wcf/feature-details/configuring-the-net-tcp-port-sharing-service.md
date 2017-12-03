---
title: "Net.TCP Port Sharing Service 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6dd81fa-68b7-4e1b-868e-88e5901b7ea0
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0932494e1d64192070db0177c35b4eb03496bebb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-the-nettcp-port-sharing-service"></a><span data-ttu-id="c388f-102">Net.TCP Port Sharing Service 구성</span><span class="sxs-lookup"><span data-stu-id="c388f-102">Configuring the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="c388f-103">Net.TCP 전송을 사용하는 자체 호스팅 서비스는 네트워크 통신에 사용되는 기본 TCP 소켓의 동작을 제어하는 `ListenBacklog` 및 `MaxPendingAccepts` 등 여러 고급 설정을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-103">Self-hosted services that use the Net.TCP transport can control several advanced settings, such as `ListenBacklog` and `MaxPendingAccepts`, which govern the behavior of the underlying TCP socket used for network communication.</span></span> <span data-ttu-id="c388f-104">그러나 전송 바인딩이 기본적으로 활성화되는 포트 공유를 사용할 수 없도록 설정한 경우 각 소켓에 대한 이러한 설정은 바인딩 수준에서만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-104">However, these settings for each socket only apply at the binding level if the transport binding has disabled port sharing, which is enabled by default.</span></span>  
  
 <span data-ttu-id="c388f-105">net.tcp 바인딩이 전송 바인딩 요소에서 `portSharingEnabled =true`로 설정하여 포트 공유를 사용할 수 있는 경우 암시적으로 외부 프로세스(즉, Net.TCP Port Sharing Service를 호스트하는 SMSvcHost.exe)가 net.tcp 바인딩 대신 TCP 소켓을 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-105">When a net.tcp binding enables port sharing (by setting `portSharingEnabled =true` on the transport binding element), it implicitly allows an external process (namely the SMSvcHost.exe, which hosts the Net.TCP Port Sharing Service) to manage the TCP socket on its behalf.</span></span> <span data-ttu-id="c388f-106">예를 들어, TCP를 사용하는 경우 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-106">For example, when using TCP, specify:</span></span>  
  
```xml  
    <tcpTransport   
        portSharingEnabled="true"  
/>  
```  
  
 <span data-ttu-id="c388f-107">이 방법으로 구성된 경우 서비스 전송 바인딩 요소에 지정된 소켓 설정은 SMSvcHost.exe에서 지정한 소켓 설정으로 인해 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-107">When configured in this way, any socket settings specified on the service's transport binding element are ignored in favor of the socket settings specified by SMSvcHost.exe.</span></span>  
  
 <span data-ttu-id="c388f-108">SMSvcHost.exe를 구성하려면 SmSvcHost.exe.config라고 하는 XML 구성 파일을 만들어 SMSvcHost.exe 실행 파일과 동일한 실제 디렉터리(예: C:\Windows\Microsoft.NET\Framework\v4.5)에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-108">To configure the SMSvcHost.exe, create an XML configuration file named SmSvcHost.exe.config and place it in the same physical directory as the SMSvcHost.exe executable (for example, C:\Windows\Microsoft.NET\Framework\v4.5).</span></span>  
  
 <span data-ttu-id="c388f-109">다음 예제에서는 명시적으로 지정된 모든 구성 가능한 값에 대한 기본 설정을 사용하여 샘플 SMSvcHost.exe.config를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-109">The following example illustrates a sample SMSvcHost.exe.config, with the default settings for all configurable values stated explicitly.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="16" <!—16 * # of processors -->  
          maxPendingAccepts="4"<!— 4 * # of processors -->  
          maxPendingConnections="100"  
          receiveTimeout="00:00:30" <!—30 seconds -->  
          teredoEnabled="false">  
          <allowAccounts>  
             <!-- LocalSystem account -->  
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->  
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->  
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->  
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only) -->  
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
</configuration>  
```  
  
## <a name="when-to-modify-smsvchostexeconfig"></a><span data-ttu-id="c388f-110">SMSvcHost.exe.config 수정 시기</span><span class="sxs-lookup"><span data-stu-id="c388f-110">When to Modify SMSvcHost.exe.config</span></span>  
 <span data-ttu-id="c388f-111">일반적으로 SMSvcHost.exe.config 파일에 지정된 구성 설정은 Net.TCP Port Sharing Service를 사용하는 컴퓨터의 모든 서비스에 영향을 주기 때문에 이 파일의 내용을 수정하는 경우 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-111">In general, care should be taken when modifying the contents of the SMSvcHost.exe.config file, because any configuration settings specified in this file affect all of the services on a computer that uses the Net.TCP Port Sharing Service.</span></span> <span data-ttu-id="c388f-112">여기에는 WAS(Windows Process Activation Service)의 TCP 활성화 기능을 사용하는 [!INCLUDE[wv](../../../../includes/wv-md.md)]의 응용 프로그램이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-112">This includes applications on [!INCLUDE[wv](../../../../includes/wv-md.md)] that use the TCP Activation features of the Windows Process Activation Service (WAS).</span></span>  
  
 <span data-ttu-id="c388f-113">그러나 Net.TCP Port Sharing Service의 기본 구성을 변경해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-113">However, sometimes you may need to change the default configuration for the Net.TCP Port Sharing Service.</span></span> <span data-ttu-id="c388f-114">예를 들어 `maxPendingAccepts`의 기본값은 4 * 프로세서 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-114">For example, the default value for `maxPendingAccepts` is 4 * number of processors.</span></span> <span data-ttu-id="c388f-115">포트 공유를 사용하는 여러 서비스를 호스트하는 서버의 경우 최대 처리량을 달성하려면 이 값을 높여야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-115">Servers that host a large number of services that use port sharing may increase this value to achieve maximum throughput.</span></span> <span data-ttu-id="c388f-116">`maxPendingConnections`의 기본값은 100입니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-116">The default value for `maxPendingConnections` is 100.</span></span> <span data-ttu-id="c388f-117">서비스를 호출하는 동시 클라이언트가 여러 개이고 서비스가 클라이언트 연결을 차단하는 경우에도 이 값을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-117">You should consider increasing this value also if there are multiple concurrent clients calling the service and the service is dropping client connections.</span></span>  
  
 <span data-ttu-id="c388f-118">또한 SMSvcHost.exe.config에는 포트 공유 서비스를 사용할 수 있는 프로세스 ID에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-118">SMSvcHost.exe.config also contains information about the process identities that may make use of the port sharing service.</span></span> <span data-ttu-id="c388f-119">프로세스가 공유 TCP 포트를 사용하기 위해 포트 공유 서비스에 연결된 경우 포트 공유 서비스를 사용하도록 허용된 ID 목록과 비교하여 연결 프로세스의 프로세스 ID를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-119">When a process connects to the port sharing service to make use of a shared TCP port, the process identity of the connecting process is checked against a list of identities that are permitted to make use of the port sharing service.</span></span> <span data-ttu-id="c388f-120">이러한 id에 보안 식별자 (Sid)로 지정 된 된 \<allowAccounts > SMSvcHost.exe.config 파일의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-120">These identities are specified as security identifiers (SIDs) in the \<allowAccounts> section of the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="c388f-121">기본적으로 포트 공유 서비스를 사용할 수 있는 권한이 Administrators 그룹의 구성원뿐만 아니라 시스템 계정(LocalService, LocalSystem 및 NetworkService)에 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-121">By default, permission to use the port sharing service is granted to system accounts (LocalService, LocalSystem, and NetworkService) as well as members of the Administrators group.</span></span> <span data-ttu-id="c388f-122">포트 공유 서비스에 연결하기 위해 다른 ID(예를 들어 사용자 ID)로 프로세스를 실행할 수 있는 응용 프로그램은 명시적으로 해당 SID를 SMSvcHost.exe.config에 추가해야 합니다. 이러한 변경 사항은 SMSvc.exe 프로세스를 다시 시작할 때까지 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-122">Applications that allow a process running as another identity (for example, a user identity) to connect to the port sharing service must explicitly add the appropriate SID to the SMSvcHost.exe.config (these changes are not applied until the SMSvc.exe process is restarted).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c388f-123">UAC(사용자 계정 컨트롤)가 활성화된 상태의 [!INCLUDE[wv](../../../../includes/wv-md.md)] 시스템에서 로컬 사용자는 해당 계정이 Administrators 그룹의 구성원인 경우에도 상승된 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-123">On [!INCLUDE[wv](../../../../includes/wv-md.md)] systems with User Account Control (UAC) enabled, local users require elevated permissions even if their account is a member of the Administrators group.</span></span> <span data-ttu-id="c388f-124">이러한 사용자를 진행할 수 있도록 포트 공유 서비스 사용자의 SID (또는 사용자가 구성원 인 그룹의 SID) 권한 상승 없이 사용에 명시적으로 추가 되어야 합니다는 \<allowAccounts > SMSvcHost.exe.config의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-124">To allow these users to make use of the port sharing service without elevation, the user's SID (or the SID of a group in which the user is a member) must be explicitly added to the \<allowAccounts> section of SMSvcHost.exe.config.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="c388f-125">기본 SMSvcHost.exe.config 파일은 사용자 지정 `etwProviderId`를 지정하여 SMSvcHost.exe 추적이 서비스 추적을 방해하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c388f-125">The default SMSvcHost.exe.config file specifies a custom `etwProviderId` to prevent SMSvcHost.exe tracing from interfering with service traces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c388f-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c388f-126">See Also</span></span>  
 [<span data-ttu-id="c388f-127">\<net.tcp ></span><span class="sxs-lookup"><span data-stu-id="c388f-127">\<net.tcp></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)
