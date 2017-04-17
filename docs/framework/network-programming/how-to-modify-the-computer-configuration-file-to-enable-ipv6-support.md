---
title: "방법: IPv6 지원을 사용하도록 컴퓨터 구성 파일 수정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
caps.latest.revision: 18
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# 방법: IPv6 지원을 사용하도록 컴퓨터 구성 파일 수정
다음 코드 예제에서는 컴퓨터 구성 파일을 수정 하는 방법을 보여 줍니다.  *machine.config*, IPv6 지원을 사용 하도록 설정 합니다.  *Machine.config* 파일에 저장 되는  *%Windir%\\Microsoft.NET\\Framework* 디렉터리에 Windows 설치 폴더.  별도  *machine.config* 파일 폴더에서  *%Windir%\\Microsoft.NET\\Framework* 의.NET Framework가 설치 된 각 버전에 대 한 \(예를 들어,  *C:\\WINDOWS\\Microsoft.NET\\Framework\\v2.0.50727\\machine.config*\).  
  
 이 설정은 컴퓨터 구성 파일 보다 우선 순위가 있는 응용 프로그램의 구성 파일에도 만들 수 있습니다.  
  
 .NET Framework 버전 1.1이 하에서의 값에 대 한는 **ipv6 enabled** 구성 스위치를 지정 여부의 멤버는 <xref:System.Net.Dns?displayProperty=fullName> 클래스 IPv6 주소를 반환 합니다.  
  
 .NET Framework 버전 2.0 및 이후 Windows IPv6, 다음의 모든 멤버를 지 원하는 경우에 <xref:System.Net.Dns?displayProperty=fullName> 클래스 \(예를 들어,는 <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=fullName> 메서드\)를 한 가지 제한 사항은 IPv6 주소를 반환 합니다.  사용 되지 않는 멤버를 <xref:System.Net.Dns?displayProperty=fullName> 클래스 \(예를 들어,는 <xref:System.Net.Dns.Resolve%2A?displayProperty=fullName> 메서드\) 읽고 구성 파일의 값을 인식 합니다.  
  
> [!NOTE]
>  .NET Framework 2.0 이상 버전에서 기본적으로 IPv6 사용 가능 합니다.  .NET Framework 버전 1.1이 하에서 i p v 6은 기본적으로 비활성화 됩니다.  
  
## 예제  
  
```  
<system.net>  
    …………  
    <settings>  
        …………  
        <ipv6 enabled="true"/>   
    ……………  
    </settings>  
    ………………  
<system.net>  
```  
  
## 참고 항목  
 [IPv6 주소 지정](../../../docs/framework/network-programming/ipv6-addressing.md)   
 [네트워크 설정 스키마](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [\<ipv6\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)