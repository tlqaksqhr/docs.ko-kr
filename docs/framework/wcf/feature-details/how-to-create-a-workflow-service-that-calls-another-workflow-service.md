---
title: "방법: 다른 워크플로 서비스를 호출하는 워크플로 서비스 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 방법: 다른 워크플로 서비스를 호출하는 워크플로 서비스 만들기
워크플로 서비스에서 다른 워크플로 서비스의 정보를 얻어야 하는 경우가 가끔 있습니다.이 항목에서는 워크플로 서비스 간에 호출하는 방법을 보여 줍니다.이 항목에서는 두 개의 워크플로 서비스를 만듭니다. 하나는 입력 문자열의 방향을 반대로 바꾸는 메서드가 있는 서비스이고, 다른 하나는 첫 번째 서비스를 사용하는 문자열의 방향을 반대로 바꾼 후 입력 문자열을 대문자로 변환하는 서비스입니다.  
  
### Reverser 워크플로 서비스를 만들려면  
  
1.  관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 실행합니다.  
  
2.  **파일** 및 **새 프로젝트**를 차례로 선택합니다.**설치된 템플릿**의 **워크플로** 노드에서 **WCF 워크플로 서비스 응용 프로그램**을 선택합니다.솔루션의 이름을 `NestedServices`로 지정하고 **확인**을 클릭합니다.  
  
3.  **서버**에서 **로컬 IIS 웹 서버 사용**이 선택되어 있는지 확인합니다.**가상 디렉터리 만들기**를 클릭합니다.가상 디렉터리가 성공적으로 만들어졌음을 나타내는 대화 상자에서 **확인**을 클릭합니다.  
  
4.  솔루션 탐색기에서 Service1.xamlx의 이름을 `StringReverserService.xamlx`로 바꿉니다.  
  
5.  새 프로젝트의 **프로젝트 속성** 페이지에서 **웹** 탭을 클릭합니다.**시작 작업**을 **특정 페이지**로 설정하고 StringReverserService.xamlx를 시작 페이지로 선택합니다.  
  
6.  디자이너에서 StringReverserService.xamlx를 열고 기존 `ReceiveRequest` 및 `SendReply` 활동을 삭제한 다음 `ReceiveAndSendReply` 활동을 기존 시퀀스 활동으로 끌어 옵니다.  
  
    1.  **OperationName**을 ReverseString으로 설정합니다.  
  
    2.  **ServiceContractName**을 IReverseString으로 설정합니다.  
  
    3.  **CanCreateInstance** 확인란을 선택합니다.  
  
7.  **SequentialService** 활동을 선택한 다음 디자이너의 아래쪽에 있는 **변수** 탭을 클릭합니다.String 형식의 StringToReverse 및 ReversedStringToReturn이라는 새로운 두 변수를 만듭니다.  
  
8.  **Receive** 활동에서 **정의** 링크를 클릭합니다.**매개 변수**를 클릭하고 StringToReverse에 할당되는 String 형식의 InputString이라는 매개 변수를 만듭니다.  
  
9. **SendReplyToReceive** 활동에서 **정의** 링크를 클릭합니다.**매개 변수**를 클릭하고 ReversedStringToReturn에 할당되는 String 형식의 ReversedString이라는 매개 변수를 만듭니다.  
  
10. 서비스의 논리를 구현하려면 프로젝트에 StringLibrary라는 새 클래스를 만듭니다.클래스 정의를 다음 코드로 바꿉니다.  
  
    ```  
    public class StringLibrary  
        {  
            public static String ReverseString(string StringToReverse)  
            {  
                char[] charArray = StringToReverse.ToCharArray();  
                Array.Reverse(charArray);  
                return new String(charArray);  
            }  
        }  
  
    ```  
  
11. 입력에 대해 ReverseString 메서드를 호출하려면 **Receive** 활동과 **SendReply** 활동 사이의 공간에 도구 상자의 **InvokeMethod** 활동을 끌어 옵니다.활동의 속성을 다음과 같이 설정합니다.  
  
    1.  **MethodName**: ReverseString  
  
    2.  **결과**: ReversedStringToReturn  
  
    3.  **매개 변수**: **방향**이 In이고 **형식**이 String이고 **값**이 StringToReverse인 새 매개 변수를 만듭니다.  
  
    4.  **TargetType**: NestedServices.StringLibrary  
  
12. F5 키를 눌러 서비스를 테스트합니다.WCF 테스트 클라이언트가 표시되면 ReverseString\(\) 메서드를 두 번 클릭합니다.요청 창에서 InputString 매개 변수 값으로 `Sample`을 입력합니다.**호출**을 클릭합니다.그러면 서비스에서 "elpmaS"를 반환합니다.  
  
### UpperCaser 워크플로 서비스를 만들려면  
  
1.  NestedServices 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** 및 **새 항목**을 차례로 선택합니다.**워크플로** 노드에서 **WCF 워크플로 서비스**를 선택하고 새로운 서비스의 이름을 `UpperCaserService`로 지정합니다.**추가**를 클릭합니다.그러면 UpperCaserService.xamlx라는 새 워크플로 서비스가 프로젝트에 추가됩니다.  
  
2.  디자이너에서 UpperCaserService.xamlx를 열고 기존 **ReceiveRequest** 및 `SendReply` 활동을 삭제한 다음 `ReceiveAndSendReply` 활동을 기존 시퀀스 활동으로 끌어 옵니다.  
  
    1.  **OperationName**을 UpperCaseString으로 설정합니다.  
  
    2.  **ServiceContractName**을 IUpperCaseString으로 설정합니다.  
  
    3.  **CanCreateInstance** 확인란을 선택합니다.  
  
3.  SequentialService 활동을 선택한 다음 디자이너의 아래쪽에 있는 **변수** 탭을 클릭합니다.String 형식의 StringToUpper, StringToReverse 및 StringToReturn이라는 세 개의 새로운 변수를 만듭니다.  
  
4.  **Receive** 활동에서 **정의** 링크를 클릭합니다.**매개 변수**를 클릭하고 StringToUpper에 할당되는 String 형식의 InputString이라는 매개 변수를 만듭니다.  
  
5.  **SendReplyToReceive** 활동에서 **정의** 링크를 클릭합니다.**매개 변수**를 클릭하고 StringToReturn에 할당되는 String 형식의 ModifiedString이라는 매개 변수를 만듭니다.  
  
6.  서비스의 논리를 구현하려면 다음 코드를 사용하여 StringLibrary 클래스에 새 메서드를 만듭니다.  
  
    ```  
    public static String UpperCaseString(string StringToUpperCase)  
    {  
         return StringToUpperCase.ToUpper();  
  
    }  
  
    ```  
  
7.  입력에 대해 UpperCaseString 메서드를 호출하려면 **Receive** 활동과 **SendReply** 활동 사이의 공간에 도구 상자의 **InvokeMethod** 활동을 끌어 옵니다.활동의 속성을 다음과 같이 설정합니다.  
  
    1.  **MethodName**: UpperCaseString  
  
    2.  **결과**: StringToReverse  
  
    3.  **매개 변수**: **방향**이 In이고 **형식**이 String이고 **값**이 StringToUpper인 새 매개 변수를 만듭니다.  
  
    4.  **TargetType**: NestedServices.StringLibrary  
  
8.  이제 수정된 문자열에 대해 첫 번째 서비스를 호출합니다.프로젝트를 마우스 오른쪽 단추로 클릭하고 **서비스 참조 추가**를 선택합니다.http:\/\/localhost\/NestedServices\/StringReverserService.xamlx에 있는 서비스에 대한 서비스 참조를 추가하고 첫 번째 서비스에 액세스하는 사용자 지정 활동을 만드는 프로젝트를 빌드합니다.  
  
9. 새 활동의 인스턴스를 워크플로에서 **InvokeMethod** 활동과 **SendReplyToReceive** 활동 사이로 끌어 옵니다.새 활동의 InputString 속성에 StringToReverse 변수를 할당하고 StringToReturn 속성에 StringToReturn 변수를 할당합니다.  
  
10. NestedServices 프로젝트의 속성 페이지를 열고 **웹** 탭에서 **특정 페이지**를 UpperCaserService.xamlx로 변경합니다.  
  
11. F5 키를 눌러 서비스를 테스트합니다.WCF 테스트 클라이언트가 표시되면 ReverseString\(\) 메서드를 두 번 클릭합니다.요청 창에서 InputString 매개 변수 값으로 `Sample`을 입력합니다.**호출**을 클릭합니다.그러면 서비스에서 "ELPMAS"를 반환합니다.  
  
### 서비스를 호출할 클라이언트를 만들려면  
  
1.  솔루션에 Client라는 새 콘솔 응용 프로그램 프로젝트를 추가합니다.  
  
2.  Client 프로젝트를 마우스 오른쪽 단추로 클릭하고 **서비스 참조 추가**를 선택합니다.창이 표시되면 **검색**을 클릭합니다.StringReverserService.xamlx를 선택하고 네임스페이스로 ReverseService를 입력합니다.**확인**을 클릭합니다.  
  
3.  Program.cs의 Main 메서드를 다음 코드로 바꿉니다.  
  
    ```  
    static void Main(string[] args)  
    {  
        Console.Write("Input string to process:");  
        String input = Console.ReadLine();  
        var service = new ReverseService.ReverseStringClient();  
        Console.WriteLine("Output from service: {0}", service.ReverseString(input));  
        Console.ReadKey();  
    }  
  
    ```