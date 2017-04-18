---
title: "memberInfoCacheCreation MDA | Microsoft Docs"
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
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "member info cache creation"
  - "MemberInfoCacheCreation MDA"
  - "reflection, run-time errors"
  - "MDAs (managed debugging assistants), cache"
  - "cache [.NET Framework], reflection"
  - "managed debugging assistants (MDAs), cache"
  - "MemberInfo cache"
ms.assetid: 5abdad23-1335-4744-8acb-934002c0b6fe
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# memberInfoCacheCreation MDA
`memberInfoCacheCreation` MDA\(관리 디버깅 도우미\)는 <xref:System.Reflection.MemberInfo> 캐시를 만들 때 활성화됩니다.  이는 프로그램에서 리소스가 많이 사용되는 리플렉션 기능이 사용되고 있음을 나타냅니다.  
  
## 증상  
 프로그램이 리소스가 많이 사용되는 리플렉션을 사용 중이므로 프로그램의 작업 집합이 증가합니다.  
  
## 원인  
 <xref:System.Reflection.MemberInfo> 개체를 포함하는 리플렉션 작업은 콜드 페이지에 저장된 메타데이터를 읽어야 하고 일반적으로 프로그램이 런타임에 바인딩 시나리오의 특정 형식을 사용 중임을 나타내므로 리소스가 많이 사용되는 것으로 간주됩니다.  
  
## 해결  
 이 MDA를 사용한 다음 디버거에서 코드를 실행하거나 MDA가 활성화될 때 디버거와 연결하면 프로그램에서 리플렉션이 사용되는 위치를 확인할 수 있습니다.  디버거에서 <xref:System.Reflection.MemberInfo> 캐시가 만들어진 위치를 보여 주는 스택 추적을 가져오고 여기서 프로그램이 리플렉션을 사용 중인 위치를 확인할 수 있습니다.  
  
 해결 방법은 코드의 목적에 따라 다릅니다.  이 MDA는 프로그램에 런타임에 바인딩 시나리오가 있음을 경고합니다.  초기에 바인딩 시나리오를 대체할 수 있는지 확인하거나 런타임에 바인딩 시나리오의 성능을 고려할 수 있습니다.  
  
## 런타임 효과  
 이 MDA는 만들어진 모든 <xref:System.Reflection.MemberInfo> 캐시에 대해 활성화됩니다.  성능의 영향은 무시할 수 있습니다.  
  
## Output  
 MDA는 <xref:System.Reflection.MemberInfo> 캐시가 만들어졌음을 나타내는 메시지를 출력합니다.  프로그램이 리플렉션을 사용하고 있는 위치를 표시하는 스택 추적을 가져오려면 디버거를 사용합니다.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## 예제  
 이 샘플 코드에서는 `memberInfoCacheCreation` MDA를 활성화합니다.  
  
```  
using System;  
  
public class Exe  
{  
    public static void Main()  
    {  
        typeof(object).GetMethods();  
    }  
}  
```  
  
## 참고 항목  
 <xref:System.Reflection.MemberInfo>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)