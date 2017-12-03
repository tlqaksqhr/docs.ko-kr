---
title: "사용자 지정 수명"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2538a9c483b949dfef1c60bd2225f5daf4e01117
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="custom-lifetime"></a>사용자 지정 수명
이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 확장을 작성하여 공유 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 인스턴스를 위한 사용자 지정 수명 서비스를 제공하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
## <a name="shared-instancing"></a>공유 인스턴스 만들기  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 서비스 인스턴스에 대한 몇 가지 인스턴스 만들기 모드를 제공합니다. 이 항목에서 설명하는 공유 인스턴스 만들기 모드를 사용하면 여러 채널 간에 서비스 인스턴스를 공유할 수 있습니다. 클라이언트에서는 인스턴스의 끝점 주소를 로컬로 확인하거나 서비스의 팩터리 메서드에 연결하여 실행 중인 인스턴스의 끝점 주소를 가져올 수 있습니다. 끝점 주소를 가져온 후에는 새 채널을 만들고 통신을 시작할 수 있습니다. 다음 코드 조각에서는 클라이언트 응용 프로그램에서 기존 서비스 인스턴스에 대한 새 채널을 만드는 방법을 보여 줍니다.  
  
```  
// Create the first channel.  
IEchoService proxy = channelFactory.CreateChannel();  
  
// Resolve the instance.  
EndpointAddress epa = ((IClientChannel)proxy).ResolveInstance();  
  
// Create new channel factory with the endpoint address resolved by   
// previous statement.  
ChannelFactory<IEchoService> channelFactory2 =  
                new ChannelFactory<IEchoService>("echoservice",  
                epa);  
  
// Create the second channel to the same instance.  
IEchoService proxy2 = channelFactory2.CreateChannel();  
```  
  
 다른 인스턴스 만들기 모드와 달리 공유 인스턴스 만들기 모드에는 서비스 인스턴스를 해제하는 고유한 방법이 있습니다. 인스턴스의 모든 채널이 닫히면 서비스 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 런타임에서는 타이머를 시작합니다. 제한 시간이 만료되기 전에 아무도 연결하지 않으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 인스턴스를 해제하고 리소스를 확보합니다. 중지 절차의 일부로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 인스턴스를 해제하기 전에 모든 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 구현의 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 메서드를 호출합니다. 모든 메서드가 `true`를 반환하면 인스턴스가 해제됩니다. 그렇지 않으면 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 구현에서 콜백 메서드를 사용하여 `Dispatcher`에 유휴 상태를 알려야 합니다.  
  
 기본적으로 <xref:System.ServiceModel.InstanceContext>의 유휴 제한 시간 값은 1분입니다. 그러나 이 샘플에서는 사용자 지정 확장을 사용하여 이 시간을 연장하는 방법을 보여 줍니다.  
  
## <a name="extending-the-instancecontext"></a>InstanceContext 확장  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 <xref:System.ServiceModel.InstanceContext>는 서비스 인스턴스와 `Dispatcher` 사이의 링크입니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 확장 가능한 개체 패턴을 사용하여 새 상태나 동작을 추가하여 이 런타임 구성 요소를 확장할 수 있습니다. 확장 가능한 개체 패턴은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 새 기능으로 기존 런타임 클래스를 확장하거나 개체에 새 상태 기능을 추가하는 데 사용됩니다. 확장 가능한 개체 패턴에는 세 가지 인터페이스인 `IExtensibleObject<T>`, `IExtension<T>` 및 `IExtensionCollection<T>`이 있습니다.  
  
 `IExtensibleObject<T>` 인터페이스는 개체의 기능을 사용자 지정하는 확장을 허용하는 개체를 통해 구현됩니다.  
  
 `IExtension<T>` 인터페이스는 `T` 형식의 클래스 확장일 수 있는 개체에 의해 구현됩니다.  
  
 마지막으로, `IExtensionCollection<T>` 인터페이스는 형식별로 `IExtensions`를 검색할 수 있게 해 주는 `IExtensions`의 컬렉션입니다.  
  
 따라서 <xref:System.ServiceModel.InstanceContext>를 확장하려면 `IExtension` 인터페이스를 구현해야 합니다. 이 샘플 프로젝트에는 `CustomLeaseExtension` 클래스에 이 구현이 포함되어 있습니다.  
  
```  
class CustomLeaseExtension : IExtension<InstanceContext>  
{  
}  
```  
  
 `IExtension` 인터페이스에는 `Attach` 및 `Detach`의 두 가지 메서드가 있습니다. 이름이 나타내듯이 이 두 메서드는 런타임에서 <xref:System.ServiceModel.InstanceContext> 클래스와 확장을 연결하거나 분리할 때 호출됩니다. 이 샘플에서는 `Attach` 메서드를 사용하여 확장의 현재 인스턴스에 속한 <xref:System.ServiceModel.InstanceContext> 개체를 추적합니다.  
  
```  
InstanceContext owner;  
  
public void Attach(InstanceContext owner)  
{  
  this.owner = owner;   
}  
```  
  
 또한 확장에 필요한 구현을 추가하여 연장된 수명 지원을 제공해야 합니다. 따라서 `ICustomLease` 인스턴스는 원하는 메서드로 선언되고 `CustomLeaseExtension` 클래스에서 구현됩니다.  
  
```  
interface ICustomLease  
{  
    bool IsIdle { get; }          
    InstanceContextIdleCallback Callback { get; set; }  
}  
  
class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease  
{  
}  
```  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 구현의 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 메서드를 호출할 경우 이 호출은 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>의 `CustomLeaseExtension` 메서드로 라우트됩니다. 그런 다음 `CustomLeaseExtension`에서 메서드의 전용 상태를 검사하여 <xref:System.ServiceModel.InstanceContext>가 유휴 상태인지 여부를 확인합니다. 유휴 상태이면 이 메서드는 `true`를 반환하며, 그렇지 않으면 연장된 수명 기간에 대한 타이머를 시작합니다.  
  
```  
public bool IsIdle  
{  
  get  
  {  
    lock (thisLock)  
    {  
      if (isIdle)  
      {  
        return true;  
      }  
      else  
      {  
        StartTimer();  
        return false;  
      }  
    }  
  }  
}  
```  
  
 타이머의 `Elapsed` 이벤트에서는 다른 정리 주기를 시작하기 위해 디스패처의 콜백 함수가 호출됩니다.  
  
```  
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)  
{  
    idleTimer.Stop();  
    isIdle = true;    
    callback(owner);  
}  
```  
  
 유휴 상태로 전환되는 인스턴스에 대해 새 메시지가 도착할 경우에는 실행 중인 타이머를 갱신할 수 없습니다.  
  
 이 샘플에서는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>을 구현하여 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 메서드에 대한 호출을 가로채고 이를 `CustomLeaseExtension`에 라우트합니다. <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 구현은 `CustomLifetimeLease` 클래스에 포함됩니다. <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 메서드는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 서비스 인스턴스를 해제하려고 할 때 호출됩니다. 그러나 ServiceBehavior의 `ISharedSessionInstance` 컬렉션에는 특정 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 구현의 인스턴스가 하나만 있습니다. 즉, <xref:System.ServiceModel.InstanceContext>에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메서드를 확인할 때 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>가 닫히는지 알 수 있는 방법이 없습니다. 따라서 이 샘플에서는 스레드 잠금을 사용하여 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 메서드에 대한 요청을 serialize합니다.  
  
> [!IMPORTANT]
>  serialization은 응용 프로그램의 성능에 큰 영향을 주므로 스레드 잠금은 사용하지 않는 것이 좋습니다.  
  
 private 멤버 변수는 `CustomLeaseExtension` 클래스에서 `IsIdle` 값을 추적하는 데 사용됩니다. <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 값이 검색될 때마다 전용 멤버 `IsIdle`이 반환되고 `false`로 다시 설정됩니다. 디스패처에서 `false` 메서드를 호출할 수 있도록 하려면 이 값을 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>로 설정해야 합니다.  
  
```  
public bool IsIdle  
{  
    get   
    {  
       lock (thisLock)  
       {  
           bool idleCopy = isIdle;  
           isIdle = false;  
           return idleCopy;  
       }  
    }  
}  
```  
  
 `ISharedSessionLifetime.IsIdle` 속성이 `false`를 반환하는 경우 디스패처에서는 `NotifyIdle` 메서드를 사용하여 콜백 함수를 등록합니다. 이 메서드는 해제되는 <xref:System.ServiceModel.InstanceContext>에 대한 참조를 받습니다. 따라서 샘플 코드에서는 `ICustomLease` 형식 확장을 쿼리하고 확장 상태의 `ICustomLease.IsIdle` 속성을 확인할 수 있습니다.  
  
```  
public void NotifyIdle(InstanceContextIdleCallback callback,   
            InstanceContext instanceContext)  
{  
    lock (thisLock)  
    {  
       ICustomLease customLease =  
           instanceContext.Extensions.Find<ICustomLease>();  
       customLease.Callback = callback;   
       isIdle = customLease.IsIdle;  
       if (isIdle)  
       {  
             callback(instanceContext);  
       }  
    }   
}  
```  
  
 `ICustomLease.IsIdle` 속성을 확인하기 전에 Callback 속성이 설정되어야 하며, 이는 `CustomLeaseExtension`이 유휴 상태가 될 때 디스패처에 이를 알리기 위해서 반드시 필요한 사항입니다. `ICustomLease.IsIdle`이 `true`를 반환하는 경우에는 `isIdle`에서 전용 멤버 `CustomLifetimeLease`이 `true`로 설정되고 callback 메서드를 호출합니다. 코드에서 잠금을 유지하므로 다른 스레드에서는 이 전용 멤버의 값을 변경할 수 없습니다. 다음에 디스패처에서 `ISharedSessionLifetime.IsIdle`을 확인할 때 이 멤버는 `true`를 반환하며 디스패처에서 인스턴스를 해제하도록 합니다.  
  
 사용자 지정 확장의 기반이 완성된 후에는 이를 서비스 모델에 후크해야 합니다. `CustomLeaseExtension` 구현을 <xref:System.ServiceModel.InstanceContext>에 후크하기 위해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> 인터페이스를 제공하여 <xref:System.ServiceModel.InstanceContext>의 부트스트래핑을 수행합니다. 샘플에서 `CustomLeaseInitializer` 클래스는 이 인터페이스를 구현하고 유일한 메서드 초기화에서 `CustomLeaseExtension` 컬렉션에 <xref:System.ServiceModel.InstanceContext.Extensions%2A>의 인스턴스를 추가합니다. 이 메서드는 <xref:System.ServiceModel.InstanceContext>를 초기화하는 동안 디스패처에서 호출됩니다.  
  
```  
public void Initialize(InstanceContext instanceContext, Message message)  
{  
  IExtension<InstanceContext> customLeaseExtension =  
    new CustomLeaseExtension(timeout);  
  instanceContext.Extensions.Add(customLeaseExtension);  
}  
```  
  
 마지막으로 `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` 및 <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> 는 구현이 모두 사용 하 여 서비스 모델까지 후크된는 <xref:System.ServiceModel.Description.IServiceBehavior> 구현 합니다. 이 구현은 `CustomLeaseTimeAttribute` 클래스에 배치되며 `Attribute` 기본 클래스에서도 파생되어 이 동작을 특성으로 노출합니다. `IServiceBehavior.ApplyBehavior` 메서드에서 <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> 및 `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` 구현의 인스턴스는 각각 `System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes`의 <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> 및 <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> 컬렉션에 추가됩니다.  
  
```  
public void ApplyBehavior(ServiceDescription description,   
           ServiceHostBase serviceHostBase,   
           Collection<DispatchBehavior> behaviors,  
           Collection<BindingParameterCollection> parameters)  
{  
    CustomLifetimeLease customLease = new CustomLifetimeLease();  
    CustomLeaseInitializer initializer =   
                new CustomLeaseInitializer(timeout);  
  
    foreach (DispatchBehavior dispatchBehavior in behaviors)  
    {  
        dispatchBehavior.InstanceContextLifetimes.Add(customLease);  
        dispatchBehavior.InstanceContextInitializers.Add(initializer);  
    }  
}  
```  
  
 `CustomLeaseTime` 특성으로 주석을 달아 이 동작을 샘플 서비스 클래스에 추가할 수 있습니다.  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Shareable)]  
[CustomLeaseTime(Timeout = 20000)]  
public class EchoService : IEchoService  
{  
  //…  
}  
```  
  
 샘플을 실행하면 작업 요청 및 응답이 서비스와 클라이언트 콘솔 창 모두에 표시됩니다. 서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`  
  
## <a name="see-also"></a>참고 항목
