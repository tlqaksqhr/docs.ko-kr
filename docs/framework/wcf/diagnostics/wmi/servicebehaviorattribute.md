---
title: "ServiceBehaviorAttribute | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# ServiceBehaviorAttribute
ServiceBehaviorAttribute  
  
## 구문  
  
```  
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## 메서드  
 ServiceBehaviorAttribute 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 ServiceBehaviorAttribute 클래스에는 다음과 같은 속성이 있습니다.  
  
### AutomaticSessionShutdown  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 클라이언트가 출력 세션을 닫을 때 세션을 자동으로 닫을지 여부를 나타냅니다.  
  
### ConcurrencyMode  
 데이터 형식: string  
액세스 형식: 읽기 전용  
  
 서비스가 하나의 스레드, 여러 개의 스레드 또는 재진입 호출을 지원할지 여부를 나타냅니다.  
  
### ConfigurationName  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 서비스 구성의 이름입니다.  
  
### IgnoreExtensionDataObject  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 네트워크에서 알 수 없는 serialization 데이터를 보낼지 여부를 지정합니다.  
  
### IncludeExceptionDetailInFaults  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 디버깅 목적으로 클라이언트에 반환되는 SOAP 오류 정보에 관리되는 예외 정보를 포함할지 여부를 지정합니다.  
  
### InstanceContextMode  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 새 서비스 개체를 만드는 시점을 지정합니다.  
  
### MaxItemsInObjectGraph  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 serialize된 개체에 허용되는 최대 항목 수입니다.  
  
### 이름  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 WSDL 서비스의 이름 특성입니다.  
  
### 네임스페이스  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 WSDL 서비스의 대상 네임스페이스입니다.  
  
### ReleaseServiceInstanceOnTransactionComplete  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 현재 트랜잭션이 완료되면 서비스 개체를 재활용할지 여부를 지정합니다.  
  
### TransactionAutoCompleteOnSessionClose  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 현재 세션이 닫히면 보류 중인 트랜잭션을 완료할지 여부를 지정합니다.  
  
### TransactionIsolationLevel  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 트랜잭션 격리 수준을 지정합니다.  
  
### TransactionTimeout  
 데이터 형식: datetime  
  
 액세스 형식: 읽기 전용  
  
 트랜잭션을 완료해야 하는 기간입니다.  
  
### UseSynchronizationContext  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 현재 동기화 컨텍스트를 사용하여 스레드 실행을 선택할지 여부를 지정합니다.  
  
### ValidateMustUnderstand  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 시스템 또는 응용 프로그램에서 SOAP MustUnderstand 헤더 처리를 적용할지 여부를 지정합니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|Namespace|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>