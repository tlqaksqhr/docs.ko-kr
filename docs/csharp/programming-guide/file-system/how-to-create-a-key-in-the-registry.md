---
title: "방법: 레지스트리에 키 만들기(Visual C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "keys, 레지스트리에서 만들기"
  - "레지스트리 키, 만들기[C#]"
  - "레지스트리, 키 및 값 추가[C#]"
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# 방법: 레지스트리에 키 만들기(Visual C#)
이 예제에서는 현재 사용자의 레지스트리에 있는 "Names" 키 아래에 "Name"과 "Isabella" 값 쌍을 추가합니다.  
  
## 예제  
  
```  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## 코드 컴파일  
  
-   코드를 복사한 다음 콘솔 응용 프로그램의 `Main` 메서드에 붙여넣습니다.  
  
-   `Names` 매개 변수를 레지스트리의 HKEY\_CURRENT\_USER 노드 바로 아래에 있는 키 이름으로 바꿉니다.  
  
-   `Nam`e 매개 변수를 Names 노드 바로 아래에 있는 값의 이름으로 바꿉니다.  
  
## 강력한 프로그래밍  
 키를 넣을 적합한 위치를 찾으려면 레지스트리 구조를 살펴 봅니다.  예를 들어, 현재 사용자의 Software 키를 열고 회사 이름을 갖는 키를 만들 수 있습니다.  그런 다음 해당 레지스트리 값을 회사 키에 추가하면 됩니다.  
  
 다음 조건에서 예외가 발생합니다.  
  
-   키 이름이 null인 경우  
  
-   사용자에게 레지스트리 키를 만들 수 있는 권한이 없는 경우  
  
-   키 이름이 255자 제한을 초과하는 경우  
  
-   키가 닫힌 경우  
  
-   레지스트리 키가 읽기 전용인 경우  
  
## .NET Framework 보안  
 데이터를 로컬 컴퓨터\(`Microsoft.Win32.Registry.LocalMachine`\)에 쓰는 것보다 사용자 폴더\(`Microsoft.Win32.Registry.CurrentUser`\)에 쓰는 것이 더 안전합니다.  
  
 레지스트리 값을 만들 때는 해당 값이 이미 존재하는 경우 어떻게 처리할 것인지 결정해야 합니다.  악의적인 프로세스가 이미 해당 값을 만들어 액세스하고 있을 수도 있습니다.  레지스트리 값에 입력한 데이터는 다른 프로세스에서도 사용할 수 있습니다.  이를 방지하려면 `Overload:Microsoft.Win32.RegistryKey.GetValue` 메서드를 사용합니다.  키가 아직 없으면 이 메서드에서 null을 반환합니다.  
  
 레지스트리 키가 ACL\(액세스 제어 목록\)에 의해 보호되는 경우에도 레지스트리에 암호 등의 비밀을 일반 텍스트로 저장하면 보안상 위험합니다.  
  
## 참고 항목  
 <xref:System.IO?displayProperty=fullName>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [파일 시스템 및 레지스트리](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)   
 [Read, write and delete from the registry with C\#](http://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)