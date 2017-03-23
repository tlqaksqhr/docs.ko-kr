---
title: "방법: CLS 규격이 아닌 예외 catch | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "예외[C#], 비CLS"
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
caps.latest.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 8
---
# 방법: CLS 규격이 아닌 예외 catch
C\+\+\/CLI를 비롯한 일부 .NET 언어에서는 개체가 <xref:System.Exception>에서 파생되지 않은 예외를 throw할 수 있습니다.  이러한 예외를 *CLS 규격이 아닌 예외* 또는 *예외가 아닌 항목*이라고 합니다.  [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)]에서는 CLS 규격이 아닌 예외를 throw할 수 없지만 다음 두 가지 방법으로 이러한 예외를 catch할 수 있습니다.  
  
-   `catch (Exception e)` 블록 내에서 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>으로 catch  
  
     기본적으로 [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)] 어셈블리에서는 CLS 규격이 아닌 예외를 래핑된 예외로 catch합니다.  <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> 속성을 통해 액세스할 수 있는 원래 예외에 액세스해야 하는 경우 이 메서드를 사용합니다.  이 항목의 뒷부분에 있는 절차에서는 이 방법으로 예외를 catch하는 방법을 설명합니다.  
  
-   `catch (Exception)` 또는 `catch (Exception e)` 블록 다음에 있는 일반적인 catch 블록\(예외 형식이 지정되지 않은 catch 블록\) 내에서 catch  
  
     CLS 규격이 아닌 예외에 대한 응답으로 로그 파일에 쓰기 등의 일부 작업을 수행하려고 하며 예외 정보에 액세스할 필요가 없는 경우 이 메서드를 사용합니다.  기본적으로 공용 언어 런타임에서는 모든 예외를 래핑합니다.  이 동작을 사용하지 않으려면 코드\(대개 AssemblyInfo.cs 파일의 코드\)에 `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`와 같이 이 어셈블리 수준의 특성을 추가합니다.  
  
### CLS 규격이 아닌 예외를 catch하려면  
  
1.  `catch(Exception e) block` 내에서 `as` 키워드를 사용하여 `e`를 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>으로 캐스팅할 수 있는지 테스트합니다.  
  
2.  <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> 속성을 통해 원래 예외에 액세스합니다.  
  
## 예제  
 다음 예제에서는 C\+\+\/CLR로 작성된 클래스 라이브러리에서 throw된 CLS 규격이 아닌 예외를 catch하는 방법을 보여 줍니다.  이 예제에서 [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)] 클라이언트 코드는 throw되는 예외 형식이 <xref:System.String?displayProperty=fullName>이라는 것을 미리 알고 있습니다.  코드에서 원래 형식에 액세스할 수 있으면 <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> 속성을 해당 형식으로 다시 캐스팅할 수 있습니다.  
  
```  
// Class library written in C++/CLR.  
   ThrowNonCLS.Class1 myClass = new ThrowNonCLS.Class1();  
  
   try  
   {  
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();   
   }  
  
   catch (Exception e)  
   {  
    RuntimeWrappedException rwe = e as RuntimeWrappedException;  
    if (rwe != null)      
    {  
      String s = rwe.WrappedException as String;  
      if (s != null)  
      {  
        Console.WriteLine(s);  
      }  
    }  
    else  
    {  
       // Handle other System.Exception types.  
    }  
   }             
```  
  
## 참고 항목  
 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>   
 [예외 및 예외 처리](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)