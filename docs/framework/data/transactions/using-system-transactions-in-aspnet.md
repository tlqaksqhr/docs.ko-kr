---
title: "ASP.NET에서 System.Transactions 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# ASP.NET에서 System.Transactions 사용
이 항목에서는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램 내부에서 <xref:System.Transactions>를 성공적으로 사용하는 방법에 대해 설명합니다.  
  
## ASP.NET에서 DistributedTransactionPermission 사용  
 <xref:System.Transactions>는 부분적으로 신뢰할 수 있는 호출자를 지원하며 **AllowPartiallyTrustedCallers** 특성\(APTCA\)으로 표시됩니다.<xref:System.Transactions>에 대한 신뢰 수준은 <xref:System.Transactions>가 노출하는 리소스 형식\(예: 시스템 메모리, 공유 프로세스 범위 리소스, 시스템 범위 리소스 및 기타 리소스\) 및 해당 리소스에 액세스하는 데 필요한 신뢰 수준을 기반으로 정의됩니다. 부분 신뢰 환경에서 완전 신뢰가 아닌 어셈블리는 <xref:System.Transactions.DistributedTransactionPermission>이 부여되지 않은 경우 응용 프로그램 도메인 내에서만 트랜잭션을 사용할 수 있습니다\(이 경우 보호되는 리소스는 시스템 메모리뿐임\).  
  
 MSDTC\(Microsoft Distributed Transaction Coordinator\)에서 관리하도록 트랜잭션 관리를 에스컬레이션할 때마다 <xref:System.Transactions.DistributedTransactionPermission>이 필요합니다. 이 종류의 시나리오에서는 프로세스 범위 리소스, 특히 MSDTC 로그의 예약된 공간인 전역 리소스를 사용합니다. 이러한 사용 예로 데이터베이스에 대한 웹 프런트 엔드 또는 제공하는 서비스의 일부로 데이터베이스를 사용하는 응용 프로그램이 있습니다.  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]에는 자체 신뢰 수준 집합이 있으며 정책 파일을 통해 특정 사용 권한 집합을 이러한 신뢰 수준과 연결합니다.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [ASP.NET Trust Levels and Policy Files](../Topic/ASP.NET%20Trust%20Levels%20and%20Policy%20Files.md). Windows SDK를 처음 설치할 때는 <xref:System.Transactions.DistributedTransactionPermission>과 연결된 기본 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 정책 파일이 없습니다. 따라서 MSDTC에서 관리하도록 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램의 트랜잭션을 에스컬레이션하는 경우 <xref:System.Transactions.DistributedTransactionPermission>을 요청할 때 <xref:System.Security.SecurityException>이 발생하며 에스컬레이션이 실패합니다.[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 부분 신뢰 환경에서 트랜잭션 에스컬레이션을 사용하려면 <xref:System.Data.SqlClient.SqlClientPermission>과 동일한 기본 신뢰 수준에서 <xref:System.Transactions.DistributedTransactionPermission>을 부여해야 합니다. 이를 지원하도록 사용자 지정 신뢰 수준과 정책 파일을 구성하거나 **Web\_hightrust.config** 및 **Web\_mediumtrust.config**인 기본 정책 파일을 수정할 수 있습니다.  
  
 정책 파일을 수정하려면 **DistributedTransactionPermission**에 대한 **SecurityClass** 요소를 **SecurityClasses** 요소의 **PolicyLevel** 요소 아래에 추가하고 해당 **IPermission** 요소를 System.Transactions에 대한 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]**NamedPermissionSet** 아래에 추가합니다. 다음 구성 파일에서 이 작업을 보여 줍니다.  
  
```  
<SecurityClasses>  
   <SecurityClass Name="DistributedTransactionPermission" Description="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
...  
</SecurityClasses>  
  
<PermissionSet  
  class="NamedPermissionSet"  
  version="1"  
  Name="ASP.Net">  
     <IPermission  
        class="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
        version="1"  
        Unrestricted="true"  
     />  
...  
</PermissionSet>  
  
```  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 보안 정책에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]은 [securityPolicy 요소\(ASP.NET 설정 스키마\)](http://msdn.microsoft.com/ko-kr/469d8d22-d263-46bb-8400-40d8d027faba)를 참조하세요.  
  
## 동적 컴파일  
 액세스 시 동적으로 컴파일되는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램에서 <xref:System.Transactions>를 가져오고 사용하려면 <xref:System.Transactions> 어셈블리에 대한 참조를 구성 파일에 넣어야 합니다. 특히 기본 루트 **Web.config** 구성 파일이나 특정 웹 응용 프로그램 구성 파일의 **compilation**\/**assemblies** 섹션 아래에 참조를 추가해야 합니다. 다음은 이에 대한 예입니다.  
  
```  
<configuration>  
   <system.web>  
      <compilation>  
         <assemblies>  
      <add assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
         </assemblies>  
      </compilation>  
   </system.web>  
</configuration>  
```  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]은 [compilation 요소의 assemblies 요소에 대한 add 요소\(ASP.NET 설정 스키마\)](http://msdn.microsoft.com/ko-kr/602197e8-108d-4249-b752-ba2a318f75e4)를 참조하세요.  
  
## 참고 항목  
 [ASP.NET Trust Levels and Policy Files](../Topic/ASP.NET%20Trust%20Levels%20and%20Policy%20Files.md)   
 [securityPolicy 요소\(ASP.NET 설정 스키마\)](http://msdn.microsoft.com/ko-kr/469d8d22-d263-46bb-8400-40d8d027faba)   
 [트랜잭션 관리 에스컬레이션 ](../../../../docs/framework/data/transactions/transaction-management-escalation.md)