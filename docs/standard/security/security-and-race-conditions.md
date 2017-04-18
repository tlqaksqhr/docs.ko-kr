---
title: "보안 및 경합 상태 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "코드 보안, 경쟁 조건"
  - "경쟁 조건"
  - "보안 코딩, 경쟁 조건"
  - "보안[.NET Framework], 경쟁 조건"
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# 보안 및 경합 상태
우려할 만한 또 다른 부분은 경합 상태에 의해 이용되는 보안 허점의 가능성입니다.  이런 가능성은 여러 가지 방식으로 나타납니다.  다음의 하위 항목에서는 개발자가 피해야 하는 주요 위험에 대해 간단히 설명합니다.  
  
## Dispose 메서드의 경합 상태  
 클래스의 **Dispose** 메서드\(자세한 내용은 [Garbage Collection](../../../docs/standard/garbage-collection/index.md) 참조\)가 동기화되어 있지 않으면 다음 예제에서처럼 **Dispose** 내부의 정리 코드가 두 번 이상 실행될 수 있습니다.  
  
```vb  
Sub Dispose()  
    If Not (myObj Is Nothing) Then  
       Cleanup(myObj)  
       myObj = Nothing  
    End If  
End Sub  
  
```  
  
```csharp  
void Dispose()   
{  
    if( myObj != null )   
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 이 **Dispose** 구현이 동기화되어 있지 않기 때문에 `Cleanup`이 첫 번째 스레드에 의해 호출된 다음 `_myObj`가 **null**로 설정되기 전에 두 번째 스레드에 의해 호출될 수 있습니다.  이것은 `Cleanup` 코드가 실행될 때 발생하는 상황에 따라 보안 문제가 될 수 있습니다.  동기화되지 않은 **Dispose** 구현에서 발생할 수 있는 주요 문제에는 파일 같은 리소스 핸들의 사용이 포함됩니다.  메서드를 잘못 사용하면 잘못된 핸들이 사용될 수 있으며 이로 인해 보안 문제가 발생할 수 있습니다.  
  
## 생성자의 경합 상태  
 일부 응용 프로그램에서는 클래스 생성자가 완전히 실행되기 전에 다른 스레드에서 클래스 멤버에 액세스할 수 있습니다.  이런 일이 발생할 경우 보안 문제가 없는지 확인하기 위해 모든 클래스 생성자를 검토하거나 필요할 경우에는 스레드를 동기화해야 합니다.  
  
## 캐시된 개체의 경합 상태  
 보안 정보를 캐시하거나 코드 액세스 보안 [Assert](../../../docs/framework/misc/using-the-assert-method.md) 작업을 사용하는 코드도 클래스의 다른 부분이 적절하게 동기화되지 않으면 경합 상태에 노출될 수 있습니다. 예를 들면 다음과 같습니다.  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False()  
    End If  
End Sub  
  
Sub DoOtherWork()  
    If fCallersOK Then  
        DoSomethingTrusted()  
    Else  
        DemandSomething()  
        DoSomethingTrusted()  
    End If  
End Sub  
  
```  
  
```csharp  
void SomeSecureFunction()   
{  
    if(SomeDemandPasses())   
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false();  
    }  
}  
void DoOtherWork()   
{  
    if( fCallersOK )   
    {  
        DoSomethingTrusted();  
    }  
    else   
    {  
        DemandSomething();  
        DoSomethingTrusted();  
    }  
}  
```  
  
 같은 개체에 대해 다른 스레드에서 호출될 수 있는 `DoOtherWork`의 다른 경로가 있으면 신뢰할 수 없는 호출자는 요청을 빠져나갈 수 있습니다.  
  
 코드가 보안 정보를 캐시하는 경우에는 이런 취약성에 대해 반드시 검토하십시오.  
  
## 종료자의 경합 상태  
 경합 상태는 이후에 종료자에서 해제되는 정적 또는 관리되지 않는 리소스를 참조하는 개체에서도 발생할 수 있습니다.  여러 개체가 클래스의 종료자에서 조작되는 리소스를 공유하는 경우 이 개체들은 해당 리소스에 대한 모든 액세스를 동기화해야 합니다.  
  
## 참고 항목  
 [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)