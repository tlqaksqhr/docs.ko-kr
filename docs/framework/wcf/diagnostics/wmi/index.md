---
title: "진단에 Windows Management Instrumentation 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe48738d-e31b-454d-b5ec-24c85c6bf79a
caps.latest.revision: "24"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7ad39675f0ecdda4706276e112d95ffbecd409ba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-windows-management-instrumentation-for-diagnostics"></a>진단에 Windows Management Instrumentation 사용
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]는 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] WMI(Windows Management Instrumentation) 공급자를 통해 런타임으로 서비스 검사 데이터를 노출합니다.  
  
## <a name="enabling-wmi"></a>WMI 사용  
 WMI는 Microsoft에서 구현한 WBEM(Web-Based Enterprise Management) 표준입니다. [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]WMI SDK 참조 [Windows Management Instrumentation](https://msdn.microsoft.com/library/aa394582.aspx)합니다. WBEM은 응용 프로그램에서 외부 관리 도구에 관리 계측을 노출하는 방법을 지정하는 산업 표준입니다.  
  
 WMI 공급자는 WBEM 호환 인터페이스를 통해 런타임으로 계측을 노출하는 구성 요소이며, 특성/값 쌍을 가진 WMI 개체 집합으로 구성됩니다. 쌍은 다양한 단순 형식일 수 있습니다. 관리 도구는 런타임에 인터페이스를 통해 서비스에 연결될 수 있습니다. [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서는 주소, 바인딩, 동작 및 수신기와 같은 서비스 특성을 노출합니다.  
  
 응용 프로그램의 구성 파일에서 기본 제공 WMI 공급자를 활성화할 수 있습니다. 이렇게는 `wmiProviderEnabled` 특성에는 [ \<진단 >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) 에 [ \<system.serviceModel >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 섹션에서 다음 샘플에 나와 있는 것 처럼 구성입니다.  
  
```xml  
<system.serviceModel>  
    …  
    <diagnostics wmiProviderEnabled="true" />  
    …  
</system.serviceModel>  
```  
  
 이 구성 항목은 WMI 인터페이스를 노출합니다. 관리 응용 프로그램이 이 인터페이스를 통해 연결하여 응용 프로그램의 관리 계측에 액세스할 수 있습니다.  
  
## <a name="accessing-wmi-data"></a>WMI 데이터 액세스  
 다양한 방식으로 WMI 데이터에 액세스할 수 있습니다. Microsoft는 스크립트, [!INCLUDE[vbprvb](../../../../../includes/vbprvb-md.md)] 응용 프로그램, C++ 응용 프로그램 및 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 등을 위한 WMI API를 제공합니다. 자세한 내용은 참조 [WMI를 사용 하 여](http://go.microsoft.com/fwlink/?LinkId=95183)합니다.  
  
> [!CAUTION]
>  .NET Framework에서 제공한 메서드를 사용하여 WMI 데이터를 프로그래밍 방식으로 액세스하는 경우 그와 같은 메서드는 연결이 설정될 때 예외를 throw할 수 있습니다. 연결은 <xref:System.Management.ManagementObject> 인스턴스를 구성하는 동안에는 설정되지 않고, 실제 데이터 교환을 포함하는 첫 번째 요청에서 설정됩니다. 따라서 `try..catch` 블록을 사용하여 가능한 예외를 catch해야 합니다.  
  
 WMI에서 `System.ServiceModel` 추적 소스에 대한 메시지 로깅 옵션과 추적 및 메시지 로깅 수준을 변경할 수 있습니다. 에 액세스 하 여이 작업을 수행할 수 있습니다는 [AppDomainInfo](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md) 이러한 부울 속성을 노출 하는 인스턴스: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, `LogMalformedMessages`, 및 `TraceLevel`합니다. 따라서 메시지 로깅을 위한 추적 수신기를 구성하지만 이러한 옵션을 구성에서 `false`로 설정해도, 이후에 응용 프로그램 실행 시 `true`로 변경할 수 있습니다. 이를 통해 메시지 로깅을 런타임에 효과적으로 활성화할 수 있습니다. 마찬가지로 구성 파일에 메시지 로깅을 활성화하더라도, WMI를 사용하여 런타임에 메시지 로깅을 비활성화할 수 있습니다.  
  
 구성 파일에서 메시지 로깅에 대한 메시지 로깅 추적 수신기 또는 추적을 위한 `System.ServiceModel` 추적 수신기를 지정하지 않으면, WMI에서 변경이 승인되더라도 변경 내용이 적용되지 않습니다. 각 수신기를 제대로 설정에 대 한 자세한 내용은 참조 하십시오. [메시지 로깅 구성](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) 및 [추적 구성](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)합니다. 구성에 지정된 다른 모든 추적 소스의 추적 수준은 응용 프로그램이 시작되면 적용되며 변경할 수 없습니다.  
  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]는 스크립트를 위한 `GetOperationCounterInstanceName` 메서드를 노출합니다. 이 메서드는 작업 이름과 함께 제공된 경우 성능 카운터 인스턴스 이름을 반환합니다. 사용자 입력을 검증하지는 않습니다. 따라서 잘못된 작업 이름을 제공하면 잘못된 카운터 이름이 반환됩니다.  
  
 `OutgoingChannel` 인스턴스의 `Service` 속성은 대상 서비스에 대한 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 클라이언트를 `Service` 메서드 내에서 만들지 않은 경우 서비스에서 다른 서비스에 연결하기 위해 연 채널 수를 계산하지 않습니다.  
  
 **주의** WMI만 지원 합니다.는 <xref:System.TimeSpan> 소수점이 하 최대 3 값입니다. 예를 들어, 서비스에서 속성 중 하나를 <xref:System.TimeSpan.MaxValue>로 설정한 경우 해당 값은 WMI를 통해 볼 때 소수점 이하 셋째 자리 이후부터 잘립니다.  
  
## <a name="security"></a>보안  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] WMI 공급자를 사용하면 환경에서 서비스를 검색할 수 있기 때문에 액세스를 허용할 때 특히 주의해야 합니다. 기본 관리자 전용 액세스를 완화하면 충분히 신뢰할 수 없는 대상이 사용자 환경의 중요 데이터에 액세스할 수 있습니다. 특히 원격 WMI 액세스에 대한 권한을 완화하면 자원 소모 공격이 발생할 수 있습니다. 과도한 WMI 요청으로 프로세스 자원이 소모되면 성능이 저하될 수 있습니다.  
  
 또한 MOF 파일에 대한 액세스 권한을 완화하면 충분히 신뢰할 수 없는 대상이 WMI 동작을 조작하고 WMI 스키마에 로드된 개체를 변경할 수 있습니다. 예를 들어, 필드를 제거하여 중요 데이터를 관리자가 보지 못하도록 숨기거나, 채워지지 않거나 예외가 발생한 필드를 파일에 추가할 수 있습니다.  
  
 기본적으로 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] WMI 공급자는 관리자에게 "실행 메서드", "공급자 쓰기" 및 "계정 사용" 권한을 부여하고 ASP.NET, Local Service 및 Network Service에 "계정 사용" 권한을 부여합니다. 특히, [!INCLUDE[wv](../../../../../includes/wv-md.md)] 이외의 플랫폼에서 ASP.NET 계정은 WMI ServiceModel 네임스페이스에 대한 읽기 권한을 가집니다. 특정 사용자 그룹에 이러한 권한을 부여하지 않으려면 WMI 공급자를 비활성화하거나(기본값) 해당 사용자 그룹에 대한 액세스 권한을 비활성화해야 합니다.  
  
 또한 구성을 통해 WMI를 활성화할 경우 사용자 권한이 부족하여 WMI가 활성화되지 않을 수도 있습니다. 그러나 이 오류를 기록하기 위해 이벤트가 이벤트 로그에 기록되지는 않습니다.  
  
 사용자 권한 수준을 수정하려면 다음 단계를 사용합니다.  
  
1.  시작을 클릭 하 고 실행 한 다음 입력 **compmgmt.msc**합니다.  
  
2.  마우스 오른쪽 단추로 클릭 **서비스 및 응용 프로그램/w m I 컨트롤** 선택할 **속성**합니다.  
  
3.  선택의 **보안** 탭으로 이동 하 고는 **Root/ServiceModel** 네임 스페이스입니다. 클릭는 **보안** 단추입니다.  
  
4.  특정 그룹이 나 액세스를 제어 하 고 사용 하려는 사용자는 **허용** 또는 **거부** 사용 권한을 구성 하려면 확인란을 선택 합니다.  
  
## <a name="granting-wcf-wmi-registration-permissions-to-additional-users"></a>추가 사용자에게 WCF WMI 등록 권한 부여  
 WCF는 “분리된 공급자”라고도 하는 in-process WMI 공급자를 호스트하여 "분리 된 공급자" 라고도 함는 in-process WMI 공급자를 호스트 하 여 수행 합니다. 노출할 관리 데이터에 대해 이 공급자를 등록하는 계정에는 적절한 사용 권한이 있어야 합니다. Windows에서는 기본적으로 권한이 있는 소수의 계정 집합만이 분리된 공급자를 등록할 수 있습니다. 그러나 사용자는 대개 기본 집합에 포함되지 않은 계정에서 실행 중인 WCF 서비스의 WMI 데이터를 노출하려고 하므로 이는 문제가 됩니다.  
  
 이 권한을 제공하려면 관리자가 다음 사용 권한을 다음과 같은 순서로 추가 계정에 부여해야 합니다.  
  
1.  WCF WMI 네임스페이스 액세스 권한  
  
2.  WCF 분리된 WMI 공급자 등록 권한  
  
#### <a name="to-grant-wmi-namespace-access-permission"></a>WMI 네임스페이스 액세스 권한을 부여하려면  
  
1.  다음 PowerShell 스크립트를 실행합니다.  
  
    ```powershell  
    write-host ""  
    write-host "Granting Access to root/servicemodel WMI namespace to built in users group"  
    write-host ""  
  
    # Create the binary representation of the permissions to grant in SDDL  
    $newPermissions = "O:BAG:BAD:P(A;CI;CCDCLCSWRPWPRCWD;;;BA)(A;CI;CC;;;NS)(A;CI;CC;;;LS)(A;CI;CC;;;BU)"  
    $converter = new-object system.management.ManagementClass Win32_SecurityDescriptorHelper  
    $binarySD = $converter.SDDLToBinarySD($newPermissions)  
    $convertedPermissions = ,$binarySD.BinarySD  
  
    # Get the object used to set the permissions  
    $security = gwmi -namespace root/servicemodel -class __SystemSecurity  
  
    # Get and output the current settings  
    $binarySD = @($null)  
    $result = $security.PsBase.InvokeMethod("GetSD",$binarySD)  
  
    $outsddl = $converter.BinarySDToSDDL($binarySD[0])  
    write-host "Previous ACL: "$outsddl.SDDL  
  
    # Change the Access Control List (ACL) using SDDL  
    $result = $security.PsBase.InvokeMethod("SetSD",$convertedPermissions)   
  
    # Get and output the current settings  
    $binarySD = @($null)  
    $result = $security.PsBase.InvokeMethod("GetSD",$binarySD)  
  
    $outsddl = $converter.BinarySDToSDDL($binarySD[0])  
    write-host "New ACL:      "$outsddl.SDDL  
    write-host ""  
    ```  
  
     이 PowerShell 스크립트는 "루트/servicemodel" WMI 네임 스페이스에 기본 제공 Users 그룹 액세스 권한을 부여할 보안 설명자 정의 언어 (SDDL)를 사용 합니다. 다음 ACL을 지정합니다.  
  
    -   BA(Built-In Administrator) – 이미 권한이 있습니다.  
  
    -   NS(Network Service) – 이미 권한이 있습니다.  
  
    -   LS(Local System) – 이미 권한이 있습니다.  
  
    -   Built-In Users – 권한을 부여할 그룹입니다.  
  
#### <a name="to-grant-provider-registration-access"></a>공급자 등록 권한을 부여하려면  
  
1.  다음 PowerShell 스크립트를 실행합니다.  
  
    ```powershell  
    write-host ""  
    write-host "Granting WCF provider registration access to built in users group"  
    write-host ""  
    # Set security on ServiceModel provider  
    $provider = get-WmiObject -namespace "root\servicemodel" __Win32Provider  
  
    write-host "Previous ACL: "$provider.SecurityDescriptor  
    $result = $provider.SecurityDescriptor = "O:BUG:BUD:(A;;0x1;;;BA)(A;;0x1;;;NS)(A;;0x1;;;LS)(A;;0x1;;;BU)"  
  
    # Commit the changes and display it to the console  
    $result = $provider.Put()  
    write-host "New ACL:      "$provider.SecurityDescriptor  
    write-host ""  
    ```  
  
### <a name="granting-access-to-arbitrary-users-or-groups"></a>임의의 사용자 또는 그룹에 권한 부여  
 이 단원의 예제에서는 모든 로컬 사용자에게 WMI 공급자 등록 권한을 부여합니다. 기본적으로 제공되지 않는 사용자 또는 그룹에게 권한을 부여하려면 해당 사용자 또는 그룹의 SID(보안 식별자)를 가져와야 합니다. 임의 사용자의 SID를 가져오는 간단한 방법은 없지만, 원하는 사용자로 로그온한 후에 다음 셸 명령을 실행하는 방법을 사용할 수 있습니다.  
  
```  
Whoami /user  
```  
  
 그러면 현재 사용자의 SID가 제공되기는 하지만, 이 방법을 통해 모든 임의 사용자의 SID를 가져올 수는 없습니다. SID를 가져오는 다른 방법을 사용 하는 것은 [getsid.exe](http://go.microsoft.com/fwlink/?LinkId=186467) 에서 도구는 [관리 작업에 대 한 Windows 2000 Resource Kit 도구](http://go.microsoft.com/fwlink/?LinkId=178660)합니다. 이 도구는 두 사용자(로컬 또는 도메인)의 SID를 비교하는데, 두 SID를 명령줄에 인쇄한다는 단점이 있습니다. [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)][잘 알려진 Sid](http://go.microsoft.com/fwlink/?LinkId=186468)합니다.  
  
## <a name="accessing-remote-wmi-object-instances"></a>원격 WMI 개체 인스턴스 액세스  
 원격 시스템에서 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] WMI 인스턴스에 액세스해야 하는 경우 액세스하는 데 사용할 도구에서 패킷 개인 정보를 활성화해야 합니다. 다음 단원에서는 WMI CIM Studio, Windows Management Instrumentation Tester 및 .NET SDK 2.0을 사용하여 이러한 작업을 수행하는 방법에 대해 설명합니다.  
  
### <a name="wmi-cim-studio"></a>WMI CIM Studio  
 설치한 경우 [WMI 관리 도구](http://go.microsoft.com/fwlink/?LinkId=95185), WMI 인스턴스에 액세스 하려면 WMI CIM Studio를 사용할 수 있습니다. 도구는 다음 폴더에 있습니다.  
  
 **%windir%\Program Files\WMI 도구\\**  
  
1.  에 **네임 스페이스에 연결:** 창, 형식 **root\ServiceModel** 클릭 **확인 합니다.**  
  
2.  에 **WMI CIM Studio 로그인** 창 클릭는 **옵션 >>** 단추 창을 확장 합니다. 선택 **패킷 개인 정보 보호** 에 대 한 **인증 수준**를 클릭 하 고 **확인**합니다.  
  
### <a name="windows-management-instrumentation-tester"></a>Windows Management Instrumentation Tester  
 이 도구는 Windows에 설치됩니다. 를 실행 하려면를 입력 하 여 명령 콘솔을 시작 **cmd.exe** 에 **시작/실행** 대화 상자와 클릭 **확인**합니다. 그런 다음 입력 **wbemtest.exe** 명령 창에서. Windows Management Instrumentation Tester 도구가 시작됩니다.  
  
1.  클릭는 **연결** 창의 오른쪽 위 단추입니다.  
  
2.  새 창에서 입력 **root\ServiceModel** 에 대 한는 **Namespace** 필드 및 선택 **패킷 개인 정보 보호** 에 대 한 **인증 수준**합니다. **연결**을 클릭합니다.  
  
### <a name="using-managed-code"></a>관리 코드 사용  
 <xref:System.Management> 네임스페이스에서 제공한 클래스를 사용하여 원격 WMI 인스턴스를 프로그래밍 방식으로 액세스할 수도 있습니다. 다음 코드 샘플에서는 이를 수행하는 방법을 보여 줍니다.  
  
```  
String wcfNamespace = String.Format(@"\\{0}\Root\ServiceModel",      
   this.serviceMachineName);  
  
ConnectionOptions connection = new ConnectionOptions();  
connection.Authentication = AuthenticationLevel.PacketPrivacy;  
ManagementScope scope = new ManagementScope(this.wcfNamespace, connection);  
```
