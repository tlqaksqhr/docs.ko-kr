---
title: "연결 정보 보호 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1471f580-bcd4-4046-bdaf-d2541ecda2f4
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 연결 정보 보호
응용 프로그램 보안의 가장 중요한 목표 중 하나는 데이터 소스에 대한 액세스를 보호하는 것입니다.  연결 문자열을 안전하게 보호하지 않으면 이로 인해 보안상 취약한 부분이 생길 수 있습니다.  연결 정보를 일반 텍스트로 저장하거나 메모리에 유지하면 전체 시스템을 손상시킬 위험이 있습니다.  소스 코드에 포함된 연결 문자열은 MSIL\(Microsoft intermediate language\)을 컴파일된 어셈블리에 표시하는 [Ildasm.exe\(IL 디스어셈블러\)](../../../../docs/framework/tools/ildasm-exe-il-disassembler.md)을를 사용하여 읽을 수 있습니다.  
  
 연결 문자열과 관련된 보안 취약성은 사용된 인증 유형, 연결 문자열을 메모리와 디스크에 유지하는 방법 및 런타임에 연결 문자열을 구성하는 기술에 따라 발생됩니다.  
  
## Windows 인증 사용  
 데이터 소스에 대한 액세스를 제한하려면 사용자 ID, 암호, 데이터 소스 이름과 같은 연결 정보의 보안을 유지해야 합니다.  사용자 정보 노출을 방지하려면 되도록 Windows 인증\(*통합 보안*이라고도 함\)을 사용하는 것이 좋습니다.  Windows 인증은 `Integrated Security` 또는 `Trusted_Connection` 키워드를 사용하여 문자열에 지정되므로 사용자 ID와 암호를 사용할 필요가 없습니다.  Windows 인증을 사용하면 사용자는 Windows에서 인증되고 서버 및 데이터베이스 리소스에 대한 액세스는 Windows 사용자 및 그룹에 부여하는 권한에 따라 결정됩니다.  
  
 Windows 인증을 사용할 수 없는 상황에서는 사용자 자격 증명이 연결 문자열에 노출되므로 각별히 유의해야 합니다.  ASP.NET 응용 프로그램에서 Windows 계정을 고정 ID로 구성하여 데이터베이스 및 기타 네트워크 리소스에 연결하는 데 사용할 수 있습니다.  **web.config** 파일에서 ID 요소에 가장을 설정하고 사용자 이름과 암호를 지정합니다.  
  
```  
<identity impersonate="true"   
        userName="MyDomain\UserAccount"   
        password="*****" />  
```  
  
 고정 ID 계정은 데이터베이스에서 필수 권한만 부여된 권한이 낮은 계정이어야 합니다.  또한 사용자 이름과 암호가 일반 텍스트로 노출되지 않도록 구성 파일을 암호화해야 합니다.  
  
## UDL\(유니버설 데이터 링크\) 파일 사용 안 함  
 UDL\(유니버설 데이터 링크\) 파일에 <xref:System.Data.OleDb.OleDbConnection>에 대한 연결 문자열을 저장하지 마세요.  UDL은 일반 텍스트로 저장되므로 암호화될 수 없습니다.  UDL 파일은 응용 프로그램에 대한 외부 파일 기반 리소스이므로 .NET Framework를 사용하여 파일을 보호하거나 암호화할 수 없습니다.  
  
## 연결 문자열 작성기를 통해 삽입 공격 방지  
 연결 문자열 삽입 공격은 사용자 입력에 대해 동적 문자열 연결을 사용하여 연결 문자열을 작성할 때 발생할 수 있습니다.  사용자 입력의 유효성이 확인되지 않고 악의적인 텍스트 또는 문자를 막을 수 없는 경우 공격자가 서버에서 중요한 데이터 또는 기타 리소스에 액세스할 가능성이 있습니다.  이 문제를 해결하기 위해 ADO.NET 2.0에서는 새 연결 문자열 작성기 클래스를 도입하여 연결 문자열 구문의 유효성을 확인하고 추가 매개 변수가 사용되지 않았는지 확인합니다.  자세한 내용은 [연결 문자열 작성기](../../../../docs/framework/data/adonet/connection-string-builders.md)을 참조하세요.  
  
## Persist Security Info\=False 사용  
 `Persist Security Info`의 기본값은 false입니다. 모든 연결 문자열에서 이 기본값을 사용하는 것이 좋습니다.  `Persist Security Info`를 `true` 또는 `yes`로 설정하면 연결이 열린 다음 연결에서 사용자 ID 및 암호와 같은 보안 관련 정보를 얻을 수 있습니다.  `Persist Security Info`를 `false` 또는 `no`로 설정하면 연결을 열기 위해 보안 정보를 사용한 다음 삭제하므로 신뢰할 수 없는 소스는 보안 관련 정보에 액세스할 수 없습니다.  
  
## 구성 파일 암호화  
 연결 문자열을 구성 파일에 저장할 수도 있으며 그러면 연결 문자열을 응용 프로그램 코드에 포함할 필요가 없습니다.  구성 파일은 .NET Framework에 공통 요소 집합이 정의된 표준 XML 파일입니다.  구성 파일의 연결 문자열은 Windows 응용 프로그램의 경우 **app.config** 파일 또는 ASP.NET 응용 프로그램의 경우 **web.config** 파일에 있는 **\<connectionStrings\>** 요소 내부에 일반적으로 저장됩니다.  구성 파일의 연결 문자열을 저장, 검색 및 암호화하는 기본적인 방법에 대한 자세한 내용은 [연결 문자열 및 구성 파일](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)을 참조하세요.  
  
## 참고 항목  
 [ADO.NET 응용 프로그램 보안](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)   
 [Encrypting Configuration Information Using Protected Configuration](../Topic/Encrypting%20Configuration%20Information%20Using%20Protected%20Configuration.md)   
 [PAVE Security in Native and .NET Framework Code](http://msdn.microsoft.com/ko-kr/bd61be84-c143-409a-a75a-44253724f784)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)