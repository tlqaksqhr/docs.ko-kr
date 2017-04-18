---
title: "영속 이중 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e76d1a1-f3d8-4a0f-8746-4a322cdff6eb
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# 영속 이중
이 샘플에서는 [!INCLUDE[wf](../../../../includes/wf-md.md)]에서 메시징 활동을 사용하여 영속 이중 메시지 교환을 설정하고 구성하는 방법을 보여 줍니다.영속 이중 메시지 교환은 오랜 기간 동안 발생하는 양방향 메시지 교환입니다.메시지 교환 수명 주기는 통신 채널 수명 주기와 서비스 인스턴스의 메모리 내 수명 주기보다 길 수 있습니다.  
  
## 샘플 세부 정보  
 이 샘플에서는 [!INCLUDE[wf2](../../../../includes/wf2-md.md)]를 사용하여 구현된 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스 두 개가 영속 이중 메시지 교환을 포함하도록 구성됩니다.영속 이중 메시지 교환은 MSMQ를 통해 보내지고 [.NET Context Exchange](http://go.microsoft.com/fwlink/?LinkID=166059)를 사용하여 상호 관련되는 두 개의 단방향 메시지로 구성됩니다.메시지는 <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.Receive> 메시징 활동을 사용하여 보냅니다..NET Context Exchange는 보낸 메시지에 대한 콜백 주소를 지정하는 데 사용됩니다.두 서비스는 WAS\(Windows Process Activation Service\)를 사용하여 호스팅되고 서비스 인스턴스의 지속성을 사용하도록 구성됩니다.  
  
 첫 번째 서비스\(Service1.xamlx\)는 전송 서비스\(Service2.xamlx\)에 작업을 수행하도록 요청을 보냅니다.작업이 완료되면 Service2.xamlx가 Service1.xamlx에 작업이 완료되었음을 알립니다.워크플로 콘솔 응용 프로그램은 서비스가 수신 대기하는 큐를 설정하고 초기 시작 메시지를 보내 Service1.xamlx를 활성화합니다.Service1.xamlx는 Service2.xamlx에서 요청한 작업이 완료되었음을 나타내는 알림을 받은 후 결과를 XML 파일로 저장합니다.Service1.xamlx는 콜백 메시지를 기다리는 동안 기본 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>를 사용하여 인스턴스 상태를 지속합니다.Service2.xamlx는 Service1.xamlx에서 요청한 작업을 완료하는 과정의 일부로 인스턴스 상태를 지속합니다.  
  
 서비스에서 MSMQ를 통해 .NET Context Exchange를 사용하도록 구성하기 위해 두 서비스에서 <xref:System.ServiceModel.Channels.ContextBindingElement>와 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>로 구성된 사용자 지정 바인딩을 사용하도록 구성합니다.<xref:System.ServiceModel.Channels.ContextBindingElement>를 사용하여 콜백 주소를 지정하고, 사용자 지정 바인딩을 사용하여 보낸 모든 메시지가 있는 콜백 컨텍스트 헤더에 이 주소를 포함합니다.다음 코드 예제에서는 사용자 지정 바인딩을 정의합니다.  
  
```xml  
<configuration>  
     <system.serviceModel>  
          …  
          <bindings>  
               <customBinding>  
                    <binding name="netMsmqContextBinding">  
                         <context clientCallbackAddress="net.msmq://localhost/private/DurableDuplex/Service1.xamlx"/>  
                         <msmqTransport exactlyOnce="False">  
                              <msmqTransportSecurity msmqAuthenticationMode="None" msmqProtectionLevel="None"/>  
                         </msmqTransport>  
                    </binding>  
               </customBinding>  
          </bindings>  
          …  
     </system.serviceModel>  
</configuration>  
  
```  
  
> [!NOTE]
>  이 샘플에서 사용하는 바인딩은 보안 처리되어 있지 않으므로응용 프로그램을 배포할 때 응용 프로그램의 보안 요구 사항에 따라 바인딩을 구성해야 합니다.  
  
> [!NOTE]
>  이 샘플에서 사용하는 큐는 트랜잭션이 아닙니다.트랜잭션 큐를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지 교환을 설정하는 방법을 보여 주는 샘플을 보려면 [MSMQ 활성화](../../../../docs/framework/wcf/samples/msmq-activation.md) 샘플을 참조하십시오.  
  
 Service1.xamlx에서 Service2.xamlx로 보내는 메시지는 Service2.xamlx의 주소로 구성된 클라이언트 끝점과 이전에 정의된 사용자 지정 바인딩을 사용하여 보내집니다.Service2.xamlx에서 Service1.xamlx로의 콜백은 Service1.xamlx에서 보낸 콜백 컨텍스트에서 주소를 가져오므로 주소가 명시적으로 구성되지 않은 클라이언트 끝점을 사용하여 보내집니다.다음 코드 예제에서는 클라이언트 끝점을 정의합니다.  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
     <system.serviceModel>  
          …  
          <client>  
               <endpoint address="net.msmq://localhost/private/DurableDuplex/Service2.xamlx" binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="IDoWork"/>  
               <endpoint binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="INotify"/>  
          </client>  
          …  
     </system.serviceModel>  
</configuration>  
  
```  
  
 다음 코드 예제에서는 net.msmq 기본 주소에 대한 기본 프로토콜 매핑을 이 사용자 지정 바인딩을 사용하도록 변경하여 이 사용자 지정 바인딩을 통해 끝점을 노출합니다.  
  
```  
<configuration>  
     <system.serviceModel>  
          <protocolMapping>  
               <add scheme="net.msmq" binding="customBinding" bindingConfiguration="netMsmqContextBinding"/>  
          </protocolMapping>  
          …  
     </system.serviceModel>  
</configuration>  
  
```  
  
 다음 코드 예제에서는 두 서비스에 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> 동작을 추가하고 지속성 데이터베이스의 연결 문자열을 지정하여 두 서비스에 지속성을 사용하도록 설정합니다.  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
    <system.serviceModel>  
          …  
          <behaviors>  
               <serviceBehaviors>  
                    <behavior>  
                         <serviceDebug includeExceptionDetailInFaults="True"/>  
                         <serviceMetadata httpGetEnabled="True"/>  
                         <sqlWorkflowInstanceStore connectionString="Data Source=.\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True"/>  
                    </behavior>  
               </serviceBehaviors>  
          </behaviors>  
     </system.serviceModel>  
</configuration>  
  
```  
  
## 시스템 요구 사항  
 이 샘플에 필요한 구성 요소는 다음과 같습니다.  
  
1.  인터넷 정보 서비스  
  
2.  인터넷 정보 서비스 \-\> IIS 6.0 관리 호환성 \-\> IIS 메타베이스 및 IIS 6.0 구성 호환성  
  
3.  World Wide Web 서비스 \-\> 응용 프로그램 개발 기능 \-\> ASP.NET  
  
4.  MSMQ\(Microsoft Message Queue\) Server  
  
#### 이 샘플을 사용하려면  
  
1.  지속성 데이터베이스와 결과 디렉터리를 설정합니다.  
  
    1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.  
  
    2.  이 샘플에서 사용할 폴더로 이동하고 Setup.cmd를 실행합니다.  
  
2.  가상 응용 프로그램을 설치합니다.  
  
    1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트에서 다음 명령을 실행하여 ASP.NET을 등록합니다.  
  
        ```  
        aspnet_regiis -i  
        ```  
  
    2.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 마우스 오른쪽 단추로 클릭하고 **관리자 권한으로 실행**을 선택하여 관리자 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 실행합니다.  
  
    3.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 DurableDuplex.sln 파일을 엽니다.  
  
3.  서비스 큐를 설정합니다.  
  
    1.  F5 키를 눌러 DurableDuplex 클라이언트를 실행합니다.  
  
    2.  명령 프롬프트에서 `Compmgmt.msc`를 실행하여 **컴퓨터 관리** 콘솔을 엽니다.  
  
    3.  **서비스 및 응용 프로그램**, **메시지 큐** 및**개인 큐**를 차례로 확장합니다.  
  
    4.  durableduplex\/service1.xamlx 및 durableduplex\/service2.xamlx 큐를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  
  
    5.  **보안** 탭을 선택하고 두 큐에 대해 **Everyone이 메시지 받기**, **메시지 보기** 및 **메시지 보내기** 권한을 갖도록 허용합니다.  
  
    6.  IIS\(인터넷 정보 서비스\) 관리자를 엽니다.  
  
    7.  **서버**, **사이트**, **기본 웹 사이트**, **개인**, **영속 이중**으로 이동하고 **고급 옵션**을 선택합니다.  
  
    8.  **사용할 수 있는 프로토콜**을 **http,net.msmq**로 변경합니다.  
  
4.  샘플을 실행합니다.  
  
    1.  http:\/\/localhost\/private\/durableduplex\/service1.xamlx 및 http:\/\/localhost\/private\/durableduplex\/service2.xamlx로 이동하여 두 서비스가 실행되고 있는지 확인합니다.  
  
    2.  F5 키를 눌러 DurableDuplexClient를 실행합니다.  
  
         영속 이중 메시지 교환이 완료되면 result.xml 파일이 C:\\Inbox 폴더에 저장되고 메시지 교환 결과를 포함합니다.  
  
#### 정리하려면\(옵션\)  
  
1.  Cleanup.cmd를 실행합니다.  
  
    1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.  
  
    2.  이 샘플에서 사용할 폴더로 이동하고 Cleanup.cmd를 실행합니다.  
  
2.  서비스의 가상 응용 프로그램을 제거합니다.  
  
    1.  명령 프롬프트에서 `Inetmgr.exe`를 실행하여 IIS\(인터넷 정보 서비스\) 관리자를 엽니다.  
  
    2.  기본 웹 사이트로 이동하고 **private** 가상 디렉터리를 제거합니다.  
  
3.  이 샘플에 사용하기 위해 설정한 큐를 제거합니다.  
  
    1.  명령 프롬프트에서 `Compmgmt.msc`를 실행하여 컴퓨터 관리 콘솔을 엽니다.  
  
    2.  **서비스 및 응용 프로그램**, **메시지 큐** 및 **개인 큐**를 차례로 확장합니다.  
  
    3.  durableduplex\/service1.xamlx 및 durableduplex\/service2.xamlx 큐를 삭제합니다.  
  
4.  C:\\Inbox 디렉터리를 제거합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDuplex`  
  
## 참고 항목