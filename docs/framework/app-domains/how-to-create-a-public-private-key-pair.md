---
title: '방법: 공개/개인 키 쌍 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- key pairs for strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- cryptographic key pairs
- snk files (key pair files)
- public-private key pairs
- .snk files
- strong-named assemblies, key pairs
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe799e15655d4ae1d9d9b7303728b503a5e45082
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-create-a-public-private-key-pair"></a>방법: 공개/개인 키 쌍 만들기
강력한 이름으로 어셈블리를 서명하려면 공개/개인 키 쌍이 있어야 합니다. 이 공개/개인 암호화 키 쌍은 컴파일 중에 강력한 이름의 어셈블리를 만드는 데 사용됩니다. [Sn.exe(강력한 이름 도구)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)를 사용하여 키 쌍을 만들 수 있습니다. 대개 키 쌍 파일의 확장명은 .snk입니다.  
  
> [!NOTE]
>  Visual Studio의 C# 및 Visual Basic 프로젝트 속성 페이지에는 Sn.exe를 사용하지 않고 기존 키 파일을 선택하거나 새 키 파일을 생성할 수 있는 **서명** 탭이 있습니다. Visual C++에서는 **속성 페이지** 창의 **구성 속성** 섹션의 **링커** 섹션에 있는 **고급** 속성 페이지에서 기존 키 파일의 위치를 지정할 수 있습니다. <xref:System.Reflection.AssemblyKeyFileAttribute> 특성을 사용하여 키 파일 쌍을 식별하는 방법은 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]부터 더 이상 사용되지 않습니다.  
  
### <a name="to-create-a-key-pair"></a>키 쌍을 만들려면  
  
1.  명령 프롬프트에 다음 명령을 입력합니다.  
  
     **sn –k** \<*file name*>  
  
     이 명령에서 *file name*은 키 쌍이 포함된 출력 파일의 이름입니다.  
  
 다음 예제에서는 `sgKey.snk`라는 키 쌍을 만듭니다.  
  
```  
sn -k sgKey.snk  
```  
  
 어셈블리 서명을 연기하고 전체 키 쌍을 제어하려는 경우(외부 테스트 시나리오가 아님), 다음 명령을 사용하여 키 쌍을 생성한 후 이 키 쌍에서 공개 키를 별도의 파일로 추출할 수 있습니다. 먼저 다음과 같이 키 쌍을 만듭니다.  
  
```  
sn -k keypair.snk  
```  
  
 그런 다음 이 키 쌍에서 공개 키를 추출하여 별도의 파일에 복사합니다.  
  
```  
sn -p keypair.snk public.snk  
```  
  
 키 쌍을 만든 후에는 강력한 이름 서명 도구에서 찾을 수 있는 위치에 이 파일을 저장해야 합니다.  
  
 강력한 이름으로 어셈블리를 서명하는 경우 [Al.exe(어셈블리 링커)](../../../docs/framework/tools/al-exe-assembly-linker.md)는 현재 디렉터리 및 출력 디렉터리와 관련된 키 파일을 검색합니다. 명령줄 컴파일러를 사용하는 경우에는, 코드 모듈이 포함된 현재 디렉터리에 키를 복사하기만 하면 됩니다.  
  
 프로젝트 속성에 **서명** 탭이 없는 이전 버전의 Visual Studio를 사용하는 경우, 권장되는 키 파일의 위치는 다음과 같이 지정된 파일 특성이 있는 프로젝트 디렉터리입니다.  
  
 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]  
  
## <a name="see-also"></a>참고 항목  
 [강력한 이름의 어셈블리 만들기 및 사용](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
