---
title: "Windows Communication Foundation 서비스에 대한 바인딩 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "바인딩 구성 [WCF]"
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
caps.latest.revision: 36
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 36
---
# Windows Communication Foundation 서비스에 대한 바인딩 구성
응용 프로그램을 만들 때 응용 프로그램의 배포 후 관리자에게 결정을 맡겨야 할 경우가 있습니다.예를 들어, 서비스 주소 또는 URI\(Uniform Resource Identifier\)가 무엇인지 미리 알 수 없는 경우가 있습니다.주소를 하드 코딩하는 대신 관리자가 서비스를 작성한 후에 이를 수행하도록 하는 것이 좋습니다.이러한 유연성은 구성을 통해 수행됩니다.  
  
> [!NOTE]
>  구성 파일을 신속하게 만들려면 `/config` 스위치와 함께 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용합니다.  
  
## 주요 섹션  
 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 구성 체계에는 `serviceModel`, `bindings` 및 `services`의 세 가지 주요 섹션이 있습니다.  
  
```  
<configuration>  
    <system.serviceModel>  
        <bindings>  
        </bindings>  
        <services>  
        </services>  
        <behaviors>  
        </behaviors>  
    </system.serviceModel>  
</configuration>  
```  
  
### ServiceModel Elements  
 `system.ServiceModel` 요소로 제한된 섹션을 사용하여 서비스의 설정뿐 아니라 하나 이상의 끝점이 있는 서비스 형식을 구성할 수 있습니다.각 끝점은 주소, 계약 및 바인딩과 함께 구성할 수 있습니다.끝점에 대한 [!INCLUDE[crabout](../../../includes/crabout-md.md)]는 [끝점 만들기 개요](../../../docs/framework/wcf/endpoint-creation-overview.md)를 참조하십시오.끝점이 지정되지 않으면 런타임에서 기본 끝점을 추가합니다.기본 끝점, 바인딩 및 동작에 대한 [!INCLUDE[crabout](../../../includes/crabout-md.md)]는 [단순화된 구성](../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스를 위한 단순화된 구성](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)을 참조하십시오.  
  
 바인딩은 전송\(HTTP, TCP, 파이프, 메시지 큐\) 및 프로토콜\(보안, 안전성, 트랜잭션 흐름\)을 지정하며, 끝점이 외부와 통신하는 방법을 지정하는 각각의 바인딩 요소로 구성됩니다.  
  
 예를 들어, [\<basicHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) 요소를 지정하면 끝점에 대한 전송으로 HTTP를 사용함을 나타냅니다.이 끝점을 사용하는 서비스가 열려 있는 경우 이 요소는 런타임에 끝점을 연결하는 데 사용됩니다.  
  
 바인딩에는 미리 정의된 바인딩 및 사용자 지정 바인딩의 두 종류가 있습니다.미리 정의된 바인딩에는 일반적인 시나리오에서 사용되는 유용한 요소의 조합이 있습니다.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서 제공하는 미리 정의된 바인딩 형식의 목록은 [시스템 제공 바인딩](../../../docs/framework/wcf/system-provided-bindings.md)을 참조하십시오.서비스 응용 프로그램에서 필요로 하는 올바른 기능의 조합을 가진 미리 정의된 바인딩 컬렉션이 없는 경우 사용자 지정 바인딩을 만들어 응용 프로그램의 요구 사항을 충족시킬 수 있습니다.사용자 지정 바인딩[!INCLUDE[crabout](../../../includes/crabout-md.md)][\<customBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)을 참조하십시오.  
  
 다음 4개의 예제에서는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 설정하는 데 사용되는 가장 일반적인 바인딩 구성을 보여 줍니다.  
  
#### 끝점을 지정하여 바인딩 형식 사용  
 첫 번째 예제에서는 주소, 계약 및 바인딩으로 구성된 끝점을 지정하는 방법을 보여 줍니다.  
  
```  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!—- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />  
  </endpoint>  
</service>  
```  
  
 이 예제에서 `name` 특성은 구성의 서비스 형식을 나타냅니다.`HelloWorld` 계약을 사용하여 코드에 서비스를 만드는 경우 서비스는 예제 구성에 정의된 모든 끝점으로 초기화됩니다.어셈블리에서 하나의 서비스 계약만 구현되는 경우 서비스는 사용 가능한 형식만 사용하므로 `name` 특성이 생략될 수 있습니다.특성에는 `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null` 형식으로 된 문자열만 있습니다.  
  
 `address` 특성은 다른 끝점이 서비스와 통신하는 데 사용하는 URI를 지정합니다.URI는 절대 경로 또는 상대 경로일 수 있습니다.상대 주소가 제공되는 경우 호스트는 바인딩에 사용된 전송 체계에 적합한 기본 주소를 제공합니다.주소가 구성되지 않으면 해당 끝점의 주소를 기본 주소로 가정합니다.  
  
 `contract` 특성은 이 끝점이 공개하는 계약을 지정합니다.서비스 구현 형식은 계약 형식을 구현해야 합니다.서비스 구현에서 단일 계약 형식을 구현하는 경우 이 속성을 생략할 수 있습니다.  
  
 `binding` 특성은 이 특정 끝점에 사용할 미리 정의된 바인딩 또는 사용자 지정 바인딩을 선택합니다.바인딩을 명시적으로 선택하지 않는 끝점에서는 기본 바인딩 선택인 `BasicHttpBinding`이 사용됩니다.  
  
#### 미리 정의된 바인딩 수정  
 다음 예제에서는 미리 정의된 바인딩을 수정합니다.그런 다음 서비스에서 끝점을 구성하는 데 해당 바인딩을 사용할 수 있습니다.바인딩은 <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> 값을 1초로 설정하여 수정합니다.속성은 <xref:System.TimeSpan> 개체를 반환합니다.  
  
 이 변경된 바인딩은 바인딩 섹션에 있습니다.끝점을 만들 때 `endpoint` 요소에 있는 `binding` 특성을 설정하면 변경된 이 바인딩을 사용할 수 있습니다.  
  
> [!NOTE]
>  바인딩에 특정 이름을 지정하는 경우 서비스 끝점에 지정된 `bindingConfiguration`이 해당 이름과 일치해야 합니다.  
  
```  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />  
  </endpoint>  
</service>  
<bindings>  
    <basicHttpBinding   
        receiveTimeout="00:00:01"  
    />  
</bindings>  
```  
  
## 서비스에 적용할 동작 구성  
 다음 예제에서는 특정 동작이 서비스 형식에 맞게 구성됩니다.`ServiceMetadataBehavior` 요소는 서비스를 쿼리하고 메타데이터에서 WSDL\(웹 서비스 기술 언어\) 문서를 생성하기 위해 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 활성화하는 데 사용됩니다.  
  
> [!NOTE]
>  동작에 특정 이름을 지정하는 경우 서비스 또는 끝점 섹션에 지정된 `behaviorConfiguration`이 해당 이름과 일치해야 합니다.  
  
```  
<behaviors>  
    <behavior>  
        <ServiceMetadata httpGetEnabled="true" />   
    </behavior>  
</behaviors>  
<services>  
    <service   
       name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
       <endpoint   
          address="http://computer:8080/Hello"  
          contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
          binding="basicHttpBinding" />  
       </endpoint>  
    </service>  
</services>  
```  
  
 위의 구성을 사용하면 클라이언트가 “HelloWorld” 형식이 지정된 서비스를 호출하고 해당 메타데이터를 가져올 수 있습니다.  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## 다른 바인딩 값을 사용하는 두 개의 끝점으로 서비스 지정  
 마지막 이 예제에서는 두 개의 끝점이 `HelloWorld` 서비스 형식에 맞게 구성됩니다.각 끝점은 동일한 바인딩 형식의 서로 다른 사용자 지정 `bindingConfiguration` 특성을 사용하며, 각 특성은 `basicHttpBinding`을 수정합니다.  
  
```  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
    <endpoint  
        address="http://computer:8080/Hello1"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="shortTimeout"  
    </endpoint>  
    <endpoint  
        address="http://computer:8080/Hello2"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="Secure"  
     </endpoint>  
</service>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure" />  
        <Security mode="Transport" />  
</bindings>  
```  
  
 다음 예제와 같이 `protocolMapping` 섹션을 추가하고 바인딩을 구성하면 기본 구성을 사용하여 같은 동작을 지정할 수 있습니다.  
  
```xml  
<protocolMapping>  
    <add scheme=”http” binding=”basicHttpBinding” bindingConfiguration=”shortTimeout” />  
    <add scheme=”https” binding=”basicHttpBinding” bindingConfiguration=”Secure” />  
</protocolMapping>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure" />  
        <Security mode="Transport" />  
</bindings>  
```  
  
## 참고 항목  
 [단순화된 구성](../../../docs/framework/wcf/simplified-configuration.md)   
 [시스템 제공 바인딩](../../../docs/framework/wcf/system-provided-bindings.md)   
 [끝점 만들기 개요](../../../docs/framework/wcf/endpoint-creation-overview.md)   
 [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)