---
title: "방법: 어셈블리 내용 보기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "어셈블리 매니페스트, 정보 보기"
  - "Ildasm.exe"
  - "MSIL 디스어셈블러"
  - "어셈블리[.NET Framework], 내용 보기"
  - "어셈블리 정보 보기"
  - "MSIL"
  - "MSIL 정보 보기"
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 어셈블리 내용 보기
[Ildasm.exe\(IL 디스어셈블러\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하면 파일에 있는 MSIL\(Microsoft Intermediate Language\) 정보를 볼 수 있습니다.  검사할 파일이 어셈블리인 경우, 이 정보에는 어셈블리 특성 이외에 다른 모듈 및 어셈블리의 참조가 포함될 수 있습니다.  이 정보는 파일이 어셈블리인지 아니면 어셈블리의 일부인지를 결정하거나 또는 다른 모듈 및 어셈블리의 참조가 파일에 포함되어 있는지를 결정하는 데 유용합니다.  
  
### Ildasm.exe를 사용하여 어셈블리의 내용을 표시하려면  
  
1.  명령 프롬프트에서 **ildasm** \<*assembly name*\> 을 입력합니다.  예를 들어, 다음 명령은 `Hello.exe` 어셈블리를 디스어셈블합니다.  
  
    ```  
    ildasm Hello.exe  
    ```  
  
### 어셈블리 매니페스트 정보를 보려면  
  
1.  MSIL 디스어셈블러 창에서 MANIFEST 아이콘을 두 번 클릭합니다.  
  
## 예제  
 다음은 간단한 "Hello, World" 예제 프로그램을 보여 줍니다.  프로그램을 컴파일한 다음 Ildasm.exe를 사용하여 Hello.exe 어셈블리를 디스어셈블하고 어셈블리 매니페스트를 봅니다.  
  
 [!code-cpp[Conceptual.Assembly.Contents#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.contents/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.Assembly.Contents#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.contents/cs/source.cs#1)]
 [!code-vb[Conceptual.Assembly.Contents#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.contents/vb/source.vb#1)]  
  
 Hello.exe 어셈블리에 대해 ildasm.exe 명령을 실행하고 IL DASM 창에서 MANIFEST 아이콘을 두 번 클릭하면 다음과 같이 출력됩니다.  
  
```  
  
// Metadata version: v4.0.30319  
.assembly extern mscorlib  
{  
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..  
  .ver 4:0:0:0  
}  
.assembly Hello  
{  
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )   
  .custom instance void [mscorlib]System.Runtime.CompilerServices.RuntimeCompatibilityAttribute::.ctor() = ( 01 00 01 00 54 02 16 57 72 61 70 4E 6F 6E 45 78   // ....T..WrapNonEx  
                                                                                                             63 65 70 74 69 6F 6E 54 68 72 6F 77 73 01 )       // ceptionThrows.  
  .hash algorithm 0x00008004  
  .ver 0:0:0:0  
}  
.module Hello.exe  
// MVID: {7C2770DB-1594-438D-BAE5-98764C39CCCA}  
.imagebase 0x00400000  
.file alignment 0x00000200  
.stackreserve 0x00100000  
.subsystem 0x0003       // WINDOWS_CUI  
.corflags 0x00000001    //  ILONLY  
// Image base: 0x00600000  
  
```  
  
 다음 표는 예제에서 사용된 Hello.exe 어셈블리의 어셈블리 매니페스트에 있는 각 지시문에 대해 설명합니다.  
  
|지시문|설명|  
|---------|--------|  
|**.assembly extern\<** assembly name**\>**|현재 모듈에서 참조되는 항목을 포함하는 또 다른 어셈블리\(이 예제에서 `mscorlib`\)를 지정합니다.|  
|**.publickeytoken \<** *token* **\>**|참조되는 어셈블리의 실제 키 토큰을 지정합니다.|  
|**.ver \<** *version number* **\>**|참조되는 어셈블리의 버전 번호를 지정합니다.|  
|**.assembly \<** *assembly name* **\>**|어셈블리 이름을 지정합니다.|  
|**.hash algorithm \<** *int32 value* **\>**|사용되는 해시 알고리즘을 지정합니다.|  
|**.ver \<** *version number* **\>**|어셈블리의 버전 번호를 지정합니다.|  
|**.module \<** *file name* **\>**|어셈블리를 구성하는 모듈의 이름을 지정합니다.  이 예제에서는 어셈블리가 하나의 파일로 구성됩니다.|  
|**.subsystem \<** *value* **\>**|프로그램에 필요한 응용 프로그램 환경을 지정합니다.  이 예제에서 값 3은 이 실행 파일이 콘솔에서 실행됨을 나타냅니다.|  
|**.corflags**|메타데이터에서 현재 예약된 파일입니다.|  
  
 어셈블리 매니페스트에는 어셈블리 콘텐츠에 따라 여러 가지 다른 지시문이 포함될 수 있습니다.  어셈블리 매니페스트의 전체 지시문 목록은 ECMA 설명서, 특히 "Partition II: Metadata Definition and Semantics" 및 "Partition III: CIL Instruction Set"를 참조하십시오.  이 설명서는 온라인에서 참고 가능합니다; MSDN의  [ECMA C\# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의  [Standard ECMA\-335 \- Common Language Infrastructure \(CLI\)](http://go.microsoft.com/fwlink/?LinkID=65552) 를 참조하십시오.  
  
## 참고 항목  
 [Application Domains and Assemblies](http://msdn.microsoft.com/ko-kr/433b04ae-4ba8-4849-9dbd-79194f240346)   
 [응용 프로그램 도메인 및 어셈블리 방법 항목](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)   
 [Ildasm.exe\(IL 디스어셈블러\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)