---
title: "클래스 | C# 가이드"
description: "클래스 형식 및 만드는 방법을 알아봅니다."
keywords: .NET, .NET Core, C#
author: BillWagner
ms.author: wiwagn
ms.date: 10/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 95c686ba-ae4f-440e-8e94-0dbd6e04d11f
ms.translationtype: Human Translation
ms.sourcegitcommit: a5ed524a1b17f7be8903f998cbd732594faab831
ms.openlocfilehash: f2cfeac321860a609c21046818c36fbc6aa3c636
ms.contentlocale: ko-kr
ms.lasthandoff: 05/15/2017

---

# <a name="classes"></a>클래스
*클래스*는 기타 형식, 메서드 및 이벤트의 변수를 그룹화하여 자체 사용자 지정 형식을 만들 수 있는 구문입니다. 클래스는 청사진과 비슷합니다. 클래스는 형식의 데이터 및 동작을 정의합니다. 클래스가 static으로 선언되지 않으면 클라이언트 코드는 변수에 할당되는 *개체* 또는 *인스턴스*를 만드는 방식으로 클래스를 사용합니다. 변수는 변수에 대한 모든 참조가 범위를 벗어날 때까지 메모리에 남아 있습니다. 이때 CLR는 변수를 가비지 수집에 적격한 것으로 표시합니다. 클래스가 [static](https://msdn.microsoft.com/library/98f28cdx.aspx)으로 선언되면 메모리에는 복사본이 하나만 존재하고 클라이언트 코드는 *인스턴스 변수*가 아니라 클래스 자체를 통해서만 클래스에 액세스할 수 있습니다. 자세한 내용은 [정적 클래스 및 정적 클래스 멤버](https://msdn.microsoft.com/library/79b3xss3.aspx)를 참조하세요.  

## <a name="reference-types"></a>참조 형식  
[클래스](https://msdn.microsoft.com/library/0b0thckt.aspx)로 정의된 형식은 *참조 형식*입니다. 런타임에 참조 형식의 변수를 선언하면 [new](https://msdn.microsoft.com/library/51y09td4.aspx) 연산자를 사용하여 개체의 인스턴스를 명시적으로 만들거나 다음 예제와 같이 [new](https://msdn.microsoft.com/library/51y09td4.aspx)를 사용하여 다른 곳에서 만들어진 개체를 할당할 때까지 변수에는 [null](https://msdn.microsoft.com/library/edakx9da.aspx) 값이 포함됩니다.  

[!code-csharp[참조 형식](../../samples/snippets/csharp/concepts/classes/reference-type.cs)]
  
개체가 만들어지면 관리되는 힙에 메모리가 할당되고 변수에는 개체 위치에 대한 참조만 포함됩니다. 관리되는 힙의 형식은 할당될 때, 그리고 *가비지 수집*이라는 CLR의 자동 메모리 관리 기능에 의해 회수될 때 오버헤드가 필요합니다. 그러나 가비지 수집은 고도로 최적화되고 대부분 시나리오에서 성능 문제를 일으키지 않습니다. 가비지 수집에 대한 자세한 내용은 [자동 메모리 관리 및 가비지 수집](../standard/garbage-collection/gc.md)을 참조하세요.  
  
참조 형식은 개체 지향 프로그래밍의 기본적인 특성인 *상속*을 완전히 지원합니다. 클래스를 만들 때 [sealed](https://msdn.microsoft.com/library/88c54tsw.aspx)로 정의되지 않은 기타 인터페이스 또는 클래스에서 상속될 수 있고 기타 클래스는 직접 만든 클래스에서 상속되고 가상 메서드를 재정의할 수 있습니다. 자세한 내용은 [상속](https://msdn.microsoft.com/library/ms173149.aspx)을 참조하세요.

## <a name="declaring-classes"></a>클래스 선언  
다음 예제와 같이 [class](https://msdn.microsoft.com/library/0b0thckt.aspx) 키워드를 사용하여 클래스를 선언합니다.  
  
[!code-csharp[클래스 선언](../../samples/snippets/csharp/concepts/classes/declaring-classes.cs)]  
  
**class** 키워드는 액세스 한정자 뒤에 옵니다. 이 경우 [public](https://msdn.microsoft.com/library/yzh058ae.aspx)이 사용되므로 누구나 이 클래스에서 개체를 만들 수 있습니다. 클래스 이름은 **class** 키워드 뒤에 옵니다. 정의의 나머지 부분은 동작과 데이터가 정의되는 클래스 본문입니다. 클래스의 필드, 속성, 메서드 및 이벤트를 모두 *클래스 멤버*라고 합니다.  
  
## <a name="creating-objects"></a>개체 만들기  
클래스는 개체의 형식을 정의하지만 개체 자체는 아닙니다. 개체는 클래스에 기반을 둔 구체적 엔터티이고 클래스의 인스턴스라고도 합니다.  
  
개체를 만들려면 다음과 같이 [new](https://msdn.microsoft.com/library/51y09td4.aspx) 키워드 뒤에 개체의 기반이 되는 클래스의 이름을 사용합니다.  
  
[!code-csharp[개체 만들기](../../samples/snippets/csharp/concepts/classes/creating-objects.cs)]   
  
클래스 인스턴스가 만들어질 때 개체에 대한 참조가 다시 프로그래머에게 전달됩니다. 이전 예제에서 `object1`은 `Customer`에 기반을 둔 개체에 대한 참조입니다. 이 참조는 새 개체를 참조하지만 개체 데이터 자체를 포함하지 않습니다. 실제로 개체를 만들지 않고도 개체 참조를 만들 수 있습니다.  
  
[!code-csharp[개체 만들기](../../samples/snippets/csharp/concepts/classes/creating-objects2.cs)]  
  
런타임에는 참조를 통한 개체 액세스 시도가 실패하므로 개체를 참조하지 않는 이와 같은 개체 참조는 만들지 않는 것이 좋습니다. 그러나 새 개체를 만들거나 다음과 같이 기존 개체에 개체를 할당하여 개체를 참조하는 참조를 만들 수 있습니다.  
  
[!code-csharp[개체 만들기](../../samples/snippets/csharp/concepts/classes/creating-objects3.cs)]  
  
이 코드에서는 같은 개체를 참조하는 두 개의 개체 참조를 만듭니다. 따라서 `object3`을 통해 이루어진 모든 개체 변경 내용은 이후 `object4` 사용 시 반영됩니다. 클래스에 기반을 둔 개체는 참조를 통해 참조되므로 클래스를 참조 형식이라고 합니다.  
  
## <a name="class-inheritance"></a>클래스 상속  
상속은 *파생*을 통해 수행합니다. 즉, 클래스는 데이터와 동작을 상속하는 소스 *기본 클래스*를 사용하여 선언됩니다. 다음과 같이 파생 클래스 이름 뒤에 콜론 및 기본 클래스 이름을 추가하여 기본 클래스를 지정합니다.  
  
[!code-csharp[상속](../../samples/snippets/csharp/concepts/classes/inheritance.cs)]  
  
기본 클래스를 선언하는 클래스는 생성자를 제외하고 기본 클래스의 모든 멤버를 상속합니다.  
  
C++와 달리 C#의 클래스는 하나의 기본 클래스에서만 직접 상속될 수 있습니다. 그러나 기본 클래스 자체는 다른 클래스에서 상속될 수 있으므로 클래스는 여러 기본 클래스를 간접적으로 상속할 수 있습니다. 게다가 클래스는 두 개 이상의 인터페이스를 직접 구현할 수 있습니다. 자세한 내용은 [인터페이스](programming-guide/interfaces/index.md)를 참조하세요.  
  
클래스는 [abstract](https://msdn.microsoft.com/library/sf985hc5.aspx)로 선언될 수 있습니다. 추상 클래스에는 시그니처 정의가 있지만 구현이 없는 추상 메서드가 포함됩니다. 추상 클래스는 인스턴스화할 수 없습니다. 추상 클래스는 추상 메서드를 구현하는 파생 클래스를 통해서만 사용할 수 있습니다. 이와 달리 [sealed](https://msdn.microsoft.com/library/88c54tsw.aspx) 클래스에서는 다른 클래스가 파생될 수 없습니다. 자세한 내용은 [추상 및 봉인 클래스와 클래스 멤버](https://msdn.microsoft.com/library/ms173150.aspx)를 참조하세요.  
  
클래스 정의는 여러 소스 파일로 분할될 수 있습니다. 자세한 내용은 [Partial 클래스 정의](https://msdn.microsoft.com/library/wa80x488.aspx)를 참조하세요.  
  
 
## <a name="example"></a>예제
다음 예제에서는 단일 필드, 메서드 및 생성자라는 특수 메서드가 포함된 public 클래스가 정의됩니다. 자세한 내용은 [생성자](https://msdn.microsoft.com/library/ace5hbzh.aspx)를 참조하세요. 그런 다음 클래스는 **new** 키워드를 사용하여 인스턴스화됩니다.

[!code-csharp[클래스 예제](../../samples/snippets/csharp/concepts/classes/class-example.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
자세한 내용은 [C# 언어 사양](https://msdn.microsoft.com/library/ms228593.aspx)을 참조하세요. C# 언어 사양은 C# 구문 및 사용법에 대한 신뢰할 수 있는 소스입니다.
  
## <a name="see-also"></a>참고 항목  
[C# 프로그래밍 가이드](https://msdn.microsoft.com/library/67ef8sbd.aspx)   
[다형성](https://msdn.microsoft.com/library/ms173152.aspx)   
[클래스 및 구조체 멤버](https://msdn.microsoft.com/library/ms173113.aspx)   
[클래스 및 구조체 메서드](https://msdn.microsoft.com/library/ms173114.aspx)   
[생성자](https://msdn.microsoft.com/library/ace5hbzh.aspx)   
[종료자](https://msdn.microsoft.com/library/66x5fx1b.aspx)   
[개체](https://msdn.microsoft.com/library/ms173110.aspx)


