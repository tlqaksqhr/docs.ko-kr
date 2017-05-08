---
title: "&lt;enforceFIPSPolicy&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<enforceFIPSPolicy> 요소"
  - "enforceFIPSPolicy 요소"
  - "FIPS(Federal Information Processing Standards)"
  - "FIPS"
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;enforceFIPSPolicy&gt; 요소
암호화 알고리즘이 FIPS\(Federal Information Processing Standard\)를 준수해야 하는 컴퓨터 구성 요구 사항에 대해 이를 적용할지 여부를 지정합니다.  
  
## 구문  
  
```  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|enabled|필수 특성입니다.<br /><br /> 암호화 알고리즘이 FIPS를 준수해야 하는 컴퓨터 구성 요구 사항에 대해 이를 적용할지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`true`|컴퓨터에 FIPS 호환 암호화 알고리즘을 요구하도록 구성한 경우 해당 요구사항이 적용됩니다.  클래스에서 FIPS와 호환되지 않는 알고리즘을 구현하는 경우 생성자 또는 해당 클래스의 `Create` 메서드는 해당 컴퓨터에서 실행 중일 때 예외를 throw합니다.  이 값이 기본값입니다.|  
|`false`|컴퓨터 구성에 관계 없이 응용 프로그램에서 사용하는 암호화 알고리즘은 FIPS를 준수할 필요가 없습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 .NET Framework 2.0으로 시작하는 경우 암호화 알고리즘을 구현하는 클래스에서는 컴퓨터의 구성에 의해 이 클래스의 생성이 제어됩니다.  컴퓨터가 FIPS와 호환되고 FIPS와 호환되지 않는 알고리즘을 구현하는 클래스를 사용하도록 구성된 경우 해당 클래스의 인스턴스를 만드는 모든 시도에서 예외가 throw됩니다.  생성자는 <xref:System.InvalidOperationException> 예외를 throw하고 `Create` 메서드는 내부 <xref:System.InvalidOperationException> 예외와 함께 <xref:System.Reflection.TargetInvocationException> 예외를 throw합니다.  
  
 FIPS를 준수해야 하는 구성이 필요한 컴퓨터에서 응용 프로그램을 실행했는데 응용 프로그램이 FIPS와 호환되지 않는 알고리즘을 사용할 경우 사용자의 구성 파일에 있는 이러한 요소를 사용하여 CLR\(공용 언어 런타임\)이 FIPS를 강제로 준수하도록 하는 것을 방지할 수 있습니다.  이 요소는 [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)]에 도입되었습니다.  
  
## 예제  
 다음 예제에서는 CLR에서 FIPS 준수를 강제 적용하지 못하도록 방지하는 방법을 보여 줍니다.  
  
```  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [암호화 모델](../../../../../docs/standard/security/cryptography-model.md)