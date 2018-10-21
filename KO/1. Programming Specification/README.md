## <font color="green">1. Programming Specification</font>
### <font color="green">명명 규약</font>
1\. **[필수]** 식별자는 '_', '$'로 시작하거나 끝날 수 없다.   
> <font color="#FF4500">반례: </font> \_name / \_\_name / \$Object / name_ / name\$ / Object\$

2\. **[필수]** Using Chinese, Pinyin, or Pinyin-English mixed spelling in naming is strictly prohibited. Accurate English spelling and grammar will make the code readable, understandable, and maintainable.   
> <font color="#019858">예시: </font> alibaba / taobao / youku / Hangzhou. In these cases, Chinese proper names in Pinyin are acceptable.

3\. **[필수]** Domain Model(DO, BO, DTO, VO, etc)을 제외한 Class명은 UpperCamelCase를 따른다.
 > <font color="#019858">예시: </font>MarcoPolo  /  UserDO  /  HtmlDTO  /  XmlService  /  TcpUdpDeal / TaPromotion  
 > <font color="#FF4500">반례: </font>marcoPolo  /  UserDo  /  HTMLDto  /  XMLService  /  TCPUDPDeal / TAPromotion  
  
4\. **[필수]** 메서드명, 전달인자명, 멤버 변수명, 지역 변수명는 lowerCamelCase를 따른다.   
> <font color="#019858">예시: </font> localValue / getHttpMessage()  /  inputUserId    


5\. **[필수]** 상수명은 대문자만 사용하며, 단어는 '_'로 구분한다. 상수명은 완전하고, 분명한 의미를 담도록 짓는다.   
> <font color="#019858">예시: </font> MAX\_STOCK\_COUNT   
> <font color="#FF4500">반례: </font> MAX\_COUNT   

6\. **[필수]** 추상 클래스는 *Abstract* 또는 *Base* 시작하도록 명명한다. 예외(Exception) 클래스는  *Exception*으로 끝나도록 명명한다. 테스트 케이스는 *테스트 대상 클래스명*으로 시작하고, *Test*로 끝나도록 명명한다.

7\. **[필수]** 괄호(Brackets) 또한 배열 타입을 선언하는 한 부분이다.
> <font color="#019858">예시: </font>*String[] args;*    
> <font color="#FF4500">반례: </font>*String args[];*    

8\. **[필수]** 몇 몇 Java Framework에서 직렬화 예외가 발생할 수 있기 때문에, Boolean 타입 멤버 변수를 정의할 때 'is' 접두사를 사용하지 않는다.  
> <font color="#FF4500">반례: </font>*boolean isSuccess;* 해당 변수에 대한 Accessors Method는 `isSuccess()`로 명명될 것이며, RPC framework(ex:XML) 는 변수명을 success로 해석하게 된다. 해당 식별자의 속성을 찾을 수 없어서 직렬화 에러가 발생하게 된다.

9\. **[필수]** 패키지명은 소문자로 명명한다. 각각의 dot('.')당 하나의 영단어만 사용한다. 패키지명은 항상 <font color="blue">단수형</font>만 허용한다. 반면, 클래스명은 필요에 따라 복수형도 가능하다. 
> <font color="#019858">예시: </font> `com.alibaba.open.util` 유틸들에 대한 패키지명으로 단수형만 사용될 수 있다.;
`MessageUtils` 클래스명으로 복수형이 사용될 수 있다.


10\. **[필수]** 의미가 쉽게 이해될 수 있도록 흔하지 않은 약어 사용은 지양한다.     
 > <font color="#FF4500">반례: </font>AbsClass (AbstractClass); condi (Condition)

11\. **[추천]**  만약 **디자인 패턴**을 사용한다면, 해당 패턴명을 클래스명에 포함시킬 수 있다.  
 > <font color="#019858">예시: </font>`public class OrderFactory;  `
`public class LoginProxy;`  `public class ResourceObserver;`  단순한 코드를 위해 interface 내 method 에는 `public`을 포함한 접근 제어자를 붙이지 않는다
> <font color="#977C00">Note: </font> 사용한 패턴명을 포함하는 클래스명은 독자의 이해를 돕는다.

12\. **[추천]** 단순한 코드를 위해 interface 내 method 에는 `public`을 포함한 접근 제어자를 붙이지 않는다. 해당 method들에 유효한 *JavaDoc* 을 작성한다. 인터페이스 내에는 **어플리케이션 공통 상수**를 제외하고는 **어떤 변수**도 선언 하지 않는다.  
 > <font color="#019858">예시: </font>method definition in the interface: `void f(); `  
constant definition: `String COMPANY = "alibaba";`    
> <font color="#977C00">Note: </font>In JDK8 it is allowed to define a default implementation for interface methods, which is valuable for all implemented classes.

13\. 인터페이스와 해당 구현체 작명에 대해 아래 두가지 규칙들을 따른다.:  
&emsp;&emsp;1) **[필수]** 모든 *Service* 와 *DAO* classe들은 반드시 SOA 규약 기반의 interface를 따른다. 구현체의 이름은 *Impl*접미사를 붙인다.  
  > <font color="#019858">예시: </font>`CacheServiceImpl` to implement `CacheService`.  
    
&emsp;&emsp;2) **[추천]** 만약 인터페이스명이 해당 인터페이스의 **능력**(ability)를 의미하게 하고 싶다면, 형용사형으로 명명한다.  
  > <font color="#019858">예시: </font>`AbstractTranslator` to implement `Translatable`.

14\. **[참조사항]** An Enumeration class name should end with *Enum*. Its members should be spelled out in upper case words, separated by underlines.  
 > <font color="#977C00">Note: </font>Enumeration is indeed a special constant class and all constructor methods are private by default.  
 > <font color="#019858">예시: </font>Enumeration name: `DealStatusEnum`; Member name: `SUCCESS  / UNKOWN_REASON`.

15\. **[참조사항]** Naming conventions for different package layers:  
&emsp;&emsp;A) Naming conventions for Service/DAO layer methods  
&emsp;&emsp;&emsp;&emsp;1) Use `get` as name prefix for a method to get a single object.  
&emsp;&emsp;&emsp;&emsp;2) Use `list` as name prefix for a method to get multiple objects.  
&emsp;&emsp;&emsp;&emsp;3) Use `count` as name prefix for a statistical method.  
&emsp;&emsp;&emsp;&emsp;4) Use `insert` or `save` (추천) as name prefix for a method to save data.  
&emsp;&emsp;&emsp;&emsp;5) Use `delete` or `remove` (추천) as name prefix for a method to remove data.  
&emsp;&emsp;&emsp;&emsp;6) Use `update` as name prefix for a method to update data.   
&emsp;&emsp;B) Naming conventions for Domain models  
&emsp;&emsp;&emsp;&emsp;1) Data Object: \*DO, where \* is the table name.  
&emsp;&emsp;&emsp;&emsp;2) Data Transfer Object: \*DTO, where \* is a domain-related name.  
&emsp;&emsp;&emsp;&emsp;3) Value Object: \*VO, where \* is a website name in most cases.  
&emsp;&emsp;&emsp;&emsp;4) POJO generally point to DO/DTO/BO/VO but cannot be used in naming as \*POJO. 

### <font color="green">Constant Conventions</font>
1\. **[필수]** Magic values, except for predefined, are forbidden in coding.       
> <font color="#FF4500">반례: </font> String key = <font color="blue">"Id#taobao_"</font> + tradeId;  

2\. **[필수]** 'L' instead of 'l' should be used for long or Long variable because 'l' is easily to be regarded as number 1 in mistake.  
> <font color="#FF4500">반례: </font>`Long a = 2l`, it is hard to tell whether it is number 21 or Long 2.

3\. **[추천]** Constants should be placed in different constant classes based on their functions. For example, cache related constants could be put in `CacheConsts` while configuration related constants could be kept in `ConfigConsts`.   
 > <font color="#977C00">Note: </font>It is difficult to find one constant in one big complete constant class.

4\. **[추천]** Constants can be shared in the following 5 different layers: *shared in multiple applications; shared inside an application;  shared in a sub-project;  shared in a package; shared in a class*.  
&emsp;&emsp;1) Shared in multiple applications: keep in  a library, under `constant` directory in client.jar;  
&emsp;&emsp;2) Shared in an application: keep in shared modules within the application, under `constant` directory;  
&emsp;&emsp;<font color="#FF4500">반례: </font>Obvious variable names should also be defined as common shared constants in an application. The following definitions caused an exception in the production environment: it returns *false*, but is expected to return *true* for `A.YES.equals(B.YES)`.  
&emsp;&emsp;Definition in Class A: `public static final String YES = "yes";`    
&emsp;&emsp;Definition in Class B: `public static final String YES = "y";`    
&emsp;&emsp;3) Shared in a sub-project: placed under `constant` directory in the current project;  
&emsp;&emsp;4) Shared in a package: placed under `constant` directory in current package;  
&emsp;&emsp;5) Shared in a class: defined as 'private static final' inside class.

5\. **[추천]** Use an enumeration class if values lie in a fixed range or if the variable has attributes. The following example shows that extra information (which day it is) can be included in enumeration:  
 > <font color="#019858">예시: </font>public Enum{ MONDAY(1), TUESDAY(2), WEDNESDAY(3), THURSDAY(4), FRIDAY(5), SATURDAY(6), SUNDAY(7);}

### <font color="green">Formatting Style</font>
1\. **[필수]** Rules for braces. If there is no content, simply use *{}* in the same line. Otherwise:    
&emsp;&emsp;1) No line break before the opening brace.   
&emsp;&emsp;2) Line break after the opening brace.     
&emsp;&emsp;3) Line break before the closing brace.   
&emsp;&emsp;4) Line break after the closing brace, *only if* the brace terminates a statement or terminates a method body, constructor or named class. There is *no*    line break after the closing brace if it is followed by `else` or a comma.

2\. **[필수]** No space is used between the '(' character and its following character. Same for the ')' character and its preceding character. Refer to the *예시* at the 5th rule.  

3\. **[필수]** There must be one space between keywords, such as if/for/while/switch, and parentheses.

4\. **[필수]** There must be one space at both left and right side of operators, such as '=', '&&', '+', '-', *ternary operator*, etc.

5\. **[필수]** Each time a new block or block-like construct is opened, the indent increases by four spaces. When the block ends, the indent returns to the previous indent level. Tab characters are not used for indentation.   
> <font color="#977C00">Note: </font>To prevent tab characters from being used for indentation, you must configure your IDE. For example, "Use tab character" should be unchecked in IDEA, "insert spaces for tabs" should be checked in Eclipse.  
> <font color="#019858">예시: </font>     
```java 
public static void main(String[] args) {
    // four spaces indent
    String say = "hello";
    // one space before and after the operator
    int flag = 0;
    // one space between 'if' and '('; 
    // no space between '(' and 'flag' or between '0' and ')'
    if (flag == 0) {
        System.out.println(say);
    }
    // one space before '{' and line break after '{'
    if (flag == 1) {
        System.out.println("world");
    // line break before '}' but not after '}' if it is followed by 'else'
    } else {  
        System.out.println("ok");
    // line break after '}' if it is the end of the block
    }
}
```

6\. **[필수]** Java code has a column limit of 120 characters. Except import statements, any line that would exceed this limit must be line-wrapped as follows:   
&emsp;&emsp;1) The second line should be intented at 4 spaces with respect to the first one. The third line and following ones should align with the second line.      
&emsp;&emsp;2) Operators should be moved to the next line together with following context.    
&emsp;&emsp;3) Character '.' should be moved to the next line together with the method after it.    
&emsp;&emsp;4) If there are multiple parameters that extend over the maximum length, a line break should be inserted after a comma.   
&emsp;&emsp;5) No line breaks should appear before parentheses.  
> <font color="#019858">예시: </font> 
```java
StringBuffer sb = new StringBuffer();
// line break if there are more than 120 characters, and 4 spaces indent at
// the second line. Make sure character '.' moved to the next line 
// together.  The third and fourth lines are aligned with the second one. 
sb.append("zi").append("xin").
    .append("huang")...
    .append("huang")...
    .append("huang");
```
> <font color="#FF4500">반례: </font>
```java
StringBuffer sb = new StringBuffer();
// no line break before '('
sb.append("zi").append("xin")...append
    ("huang");  
// no line break before ',' if there are multiple params
invoke(args1, args2, args3, ...
    , argsX);
```

7\. **[필수]** There must be one space between a comma and the next parameter for methods with multiple parameters.   
> <font color="#019858">예시: </font>One space is used after the *'<font color="blue">,</font>'* character in the following method definition.
```java
f("a", "b", "c");
```

8\. **[필수]** The charset encoding of text files should be *UTF-8* and the characters of line breaks should be in *Unix* format, instead of *Windows* format.

9\. **[추천]** It is unnecessary to align variables by several spaces.   
> <font color="#019858">예시: </font> 
```java
int a = 3;
long b = 4L;
float c = 5F;
StringBuffer sb = new StringBuffer();
```
> <font color="#977C00">Note: </font>It is cumbersome to insert several spaces to align the variables above.   

10\. **[추천]** Use a single blank line to separate sections with the same logic or semantics.
> <font color="#977C00">Note: </font>It is unnecessary to use multiple blank lines to do that.

### <font color="green">OOP Rules</font>
1\. **[필수]** A static field or method should be directly referred to by its class name instead of its corresponding object name.

2\. **[필수]** An overridden method from an interface or abstract class must be marked with `@Override` annotation.   
 > <font color="#FF4500">반례: </font>For `getObject()` and `get0bject()`, the first one has a letter 'O', and the second one has a number '0'. To accurately determine whether the overriding is successful, an `@Override` annotation is necessary. Meanwhile, once the method signature in the abstract class is changed, the implementation class will report a compile-time error immediately.

3\. **[필수]** *varargs* is 추천 only if all parameters are of the same type and semantics. Parameters with `Object` type should be avoided.  
 > <font color="#977C00">Note: </font>Arguments with the *varargs* feature must be at the end of the argument list. (Programming with the *varargs* feature is not 추천.)  
 > <font color="#019858">예시: </font>
```java
public User getUsers(String type, Integer... ids);
```

4\. **[필수]** Modifying the <font color="blue">method signature</font> is forbidden to avoid affecting the caller. A `@Deprecated` annotation with an explicit description of the new service is necessary when an interface is deprecated.

5\. **[필수]** Using a deprecated class or method is prohibited.  
 > <font color="#977C00">Note: </font>For example, `decode(String source, String encode)` should be used instead of the deprecated method `decode(String encodeStr)`. Once an interface has been deprecated, the interface provider has the obligation to provide a new one. At the same time, client programmers have  the obligation to use the new interface.

6\. **[필수]** Since `NullPointerException` can possibly be thrown while calling the *equals* method of `Object`, *equals* should be invoked by a constant or an object that is definitely not *null*.  
 > <font color="#019858">예시: </font> `"test".equals(object);`   
 > <font color="#FF4500">반례: </font> `object.equals("test");`    
 > <font color="#977C00">Note: </font>`java.util.Objects#equals` (a utility class in JDK7) is 추천. 

7\. **[필수]** Use the `equals` method, rather than reference equality '==', to compare primitive wrapper classes.
 > <font color="#977C00">Note: </font>Consider this assignment: `Integer var = ?`. When it fits the range from <font color="blue">-128 to 127</font>, we can use `==` directly for a comparison. Because the `Integer` object will be generated by `IntegerCache.cache`, which reuses an existing object. Nevertheless, when it fits the complementary set of the former range, the `Integer` object will be allocated in the heap, which does not reuse an existing object. This is a pitfall. Hence the `equals` method is 추천.
 
8\. **[필수]** Rules for using primitive data types and wrapper classes:     
&emsp;&emsp;1) Members of a POJO class must be wrapper classes.  
&emsp;&emsp;2) The return value and arguments of a RPC method must be wrapper classes.   
&emsp;&emsp;3) **[추천]** Local variables should be primitive data types.  
&emsp;&emsp;<font color="#977C00">Note: </font>In order to remind the consumer of explicit assignments, there are no initial values for members in a POJO class. As a consumer, you should check problems such as `NullPointerException` and warehouse entries for yourself.   
&emsp;&emsp;<font color="#019858">예시: </font>As the result of a database query may be *null*, assigning it to a primitive date type will cause a risk of `NullPointerException` because of autoboxing.     
&emsp;&emsp;<font color="#FF4500">반례: </font>Consider the output of a  transaction volume's amplitude, like *±x%*. As a primitive data, when it comes to a failure of calling a RPC service, the default return value: *0%* will be assigned, which is not correct. A hyphen like *-* should be assigned instead. Therefore, the *null* value of a wrapper class can represent additional information, such as a failure of calling a RPC service, an abnormal exit, etc.

9\. **[필수]** While defining POJO classes like DO, DTO, VO, etc., do not assign any <font color="blue">default values</font> to the members.   

10\. **[필수]** To avoid a deserialization failure, do not change the *serialVersionUID* when a serialized class needs to be updated, such as adding some new members. If a completely incompatible update is needed, change the value of *serialVersionUID* in case of a confusion when deserialized.  
> <font color="#977C00">Note: </font>The inconsistency of *serialVersionUID* may cause an `InvalidClassException` at runtime.

11\. **[필수]** Business logic in constructor methods is prohibited. All initializations should be implemented in the `init` method.

12\. **[필수]** The `toString` method must be implemented in a POJO class. The `super.toString` method should be called in in the beginning of the implementation if the current class extends another POJO class.
 > <font color="#977C00">Note: </font>We can call the `toString` method in a POJO directly to print property values in order to check the problem when a method throws an exception in runtime.

13\. **[추천]** When accessing an array generated by the split method in String using an index, make sure to check the last separator whether it is null to avoid `IndexOutOfBoundException`.  
> <font color="#977C00">Note: </font>
``` java
String str = "a,b,c,,";
String[] ary = str.split(",");
// The expected result exceeds 3. However it turns out to be 3.
System.out.println(ary.length);  
```

14\. **[추천]** Multiple constructor methods or homonymous methods in a class should be put together for better readability.

15\. **[추천]** The order of methods declared within a class is:  
*public or protected methods -> private methods -> getter/setter methods*.          
 > <font color="#977C00">Note: </font> As the most concerned ones for consumers and providers, *public* methods should be put on the first screen. *Protected* methods are only cared for by the subclasses, but they have chances to be vital when it comes to Template Design Pattern. *Private* methods, the black-box approaches, basically are not significant to clients. *Getter/setter* methods of a Service or a DAO should be put at the end of the class implementation because of the low significance.

16\. **[추천]** For a *setter* method, the argument name should be the same as the field name. Implementations of business logics in *getter/setter* methods, which will increase difficulties of the troubleshooting, are not 추천.  
 > <font color="#FF4500">반례: </font>
 ```java
 public Integer getData() {
     if (true) {
         return data + 100; 
     } else {
         return data - 100;
     }
 }
 ```  

17\. **[추천]** Use the `append` method in `StringBuilder` inside a loop body when concatenating multiple strings.  
 > <font color="#FF4500">반례: </font>  
```java
String str = "start";
for (int i = 0; i < 100; i++) {
    str = str + "hello";
}
```  
> <font color="#977C00">Note: </font>According to the decompiled bytecode file, for each loop, it allocates a `StringBuilder` object, appends a string, and finally returns a `String` object via the `toString` method. This is a tremendous waste of memory.

18\. **[추천]** Keyword *final* should be used in the following situations:    
&emsp;&emsp;1) A class which is not allow to be inherited, or a local variable not to be reassigned.  
&emsp;&emsp;2) An argument which is not allow to be modified.   
&emsp;&emsp;3) A method which is not allow to be overridden.

19\. **[추천]** Be cautious to copy an object using the `clone` method in `Object`.  
 > <font color="#977C00">Note: </font>The default implementation of `clone` in `Object` is a shallow (not deep) copy, which copies fields as pointers to the same objects in memory.

20\. **[추천]** Define the access level of members in class with severe  restrictions:    
&emsp;&emsp;1) Constructor methods must be `private` if an allocation using `new` keyword outside of the class is forbidden.   
&emsp;&emsp;2) Constructor methods are not allowed to be `public` or `default` in a utility class.   
&emsp;&emsp;3) Nonstatic class variables that are accessed from inheritants must be `protected`.  
&emsp;&emsp;4) Nonstatic class variables that no one can access except the class that contains them must be `private`.  
&emsp;&emsp;5) Static variables that no one can access except the class that contains them must be `private`.       
&emsp;&emsp;6) Static variables should be considered in determining whether they are `final`.  
&emsp;&emsp;7) Class methods that no one can access except the class that contains them must be `private`.  
&emsp;&emsp;8) Class methods that are accessed from inheritants must be `protected`.   
 > <font color="#977C00">Note: </font> We should strictly control the access for any classes, methods, arguments and variables. Loose access control causes harmful coupling of modules. Imagine the following situations. For a `private` class member, we can remove it as soon as we want. However, when it comes to a `public` class member, we have to think twice before any updates happen to it. 

### <font color="green">Collection</font>
1\. **[필수]** The usage of *hashCode* and *equals* should follow:   
&emsp;&emsp;1) Override *hashCode* if *equals* is overridden.  
&emsp;&emsp;2) These two methods must be overridden for elements of a `Set` since they are used to ensure that no duplicate object will be inserted in `Set`.  
&emsp;&emsp;3) These two methods must be overridden for any object that is used as the key of `Map`.  
> <font color="#977C00">Note: </font> `String` can be used as the key of `Map` since `String` defines these two methods.

2\. **[필수]** Do not add elements to collection objects returned by `keySet()`/`values()`/`entrySet()`, otherwise `UnsupportedOperationException` will be thrown. 

3\. **[필수]** Do not add nor remove to/from immutable objects returned by methods in `Collections`, e.g. `emptyList()`/`singletonList()`.    
> <font color="#FF4500">반례: </font>Adding elements to `Collections.emptyList()` will throw `UnsupportedOperationException`.

4\. **[필수]** Do not cast *subList* in class `ArrayList`, otherwise  `ClassCastException` will be thrown: `java.util.RandomAccessSubList` cannot be cast to `java.util.ArrayList`.  
 > <font color="#977C00">Note: </font>`subList` of `ArrayList` is an inner class, which is a view of `ArrayList`. All operations on the `Sublist` will affect the original list.

5\. **[필수]** When using *subList*, be careful when modifying the size of original list. It might cause `ConcurrentModificationException` when performing traversing, adding or deleting on the *subList*.   

6\. **[필수]** Use `toArray(T[] array)` to convert a list to an array. The input array type should be the same as the list whose size is `list.size()`.    
 > <font color="#FF4500">반례: </font> Do not use `toArray` method without arguments. Since the return type is `Object[]`, `ClassCastException` will be thrown when casting it to a different array type.  
> <font color="#019858">예시: </font>
```java
		List<String> list = new ArrayList<String>(2);
		list.add("guan");
		list.add("bao");		
		String[] array = new String[list.size()];
		array = list.toArray(array);
```  
> <font color="#977C00">Note: </font>When using `toArray` method with arguments, pass an input with the same size as the list.  If input array size is not large enough, the method will re-assign the size internally, and then return the address of new array. If the size is larger than needed, extra elements (`index[list.size()]` and later) will be set to *null*.

7\. **[필수]** Do not use methods which will modify the list after using `Arrays.asList` to convert array to list, otherwise methods like *add/remove/clear* will throw `UnsupportedOperationException`.   
> <font color="#977C00">Note: </font>The result of `asList` is the inner class of `Arrays`, which does not implement methods to modify itself. `Arrays.asList` is only a transferred interface, data inside which is stored as an array. 
```java
String[] str = new String[] { "a", "b" };
List<String> list = Arrays.asList(str); 
```   
 Case 1: `list.add("c");` will throw a runtime exception.  
 Case 2: `str[0]= "gujin";` `list.get(0)` will be modified.

8\. **[필수]** Method `add` cannot be used for generic wildcard with `<? Extends T>`, method `get` cannot be used with `<? super T>`, which probably goes wrong.   
> <font color="#977C00">Note: </font>About PECS (Producer Extends Consumer Super) principle:  
1) `Extends` is suitable for frequently reading scenarios.   
2) `Super` is suitable for frequently inserting scenarios.

9\. **[필수]** Do not remove or add elements to a collection in a *foreach* loop. Please use `Iterator` to remove an item. `Iterator` object should be synchronized when executing concurrent operations.  
 > <font color="#FF4500">반례: </font>
```java
List<String> a = new ArrayList<String>();
a.add("1");
a.add("2");
for (String temp : a) {
    if ("1".equals(temp)){
        a.remove(temp);
    }
}
```
> <font color="#977C00">Note: </font> If you try to replace "1" with "2", you will get an unexpected result.
> <font color="#019858">예시: </font>
```java
Iterator<String> it = a.iterator();
while (it.hasNext()) {    
    String temp =  it.next();             
    if (delete condition) {              
        it.remove();       
    }
}    
```  

10\. **[필수]** In JDK 7 and above version, `Comparator` should meet the three requirements listed below, otherwise `Arrays.sort` and `Collections.sort` will throw `IllegalArgumentException`.    
> <font color="#977C00">Note: </font>  
&emsp;&emsp;1) Comparing x,y and y,x should return the opposite result.  
&emsp;&emsp;2) If x>y and y>z, then x>z.  
&emsp;&emsp;3) If x=y, then comparing x with z and comparing y with z should return the same result.    
> <font color="#FF4500">반례: </font>The program below cannot handle the case if o1 equals to o2, which might cause an exception in a real case:  
```java
new Comparator<Student>() {
    @Override
    public int compare(Student o1, Student o2) {
        return o1.getId() > o2.getId() ? 1 : -1;
    }
}
```

11\. **[추천]** Set a size when initializing a collection if possible.    
> <font color="#977C00">Note: </font>Better to use `ArrayList(int initialCapacity)` to initialize `ArrayList`.

12\. **[추천]** Use `entrySet` instead of `keySet` to traverse KV maps.   
> <font color="#977C00">Note: </font>Actually, `keySet` iterates through the map twice, firstly convert to `Iterator` object, then get the value from the `HashMap` by key. `EntrySet` iterates only once and puts keys and values in the entry which is more efficient. Use `Map.foreach` method in JDK8.  
 > <font color="#019858">예시: </font>`values()` returns a list including all values, `keySet()` returns a set including all values, `entrySet()` returns a k-v combined object.

13\. **[추천]** Carefully check whether a *k/v collection* can store *null* value, refer to the table below:
 
 | Collection | Key | Value | Super | Note |
  | --- | --- | --- | --- | --- |
 | Hashtable | <font color="#FF4500">Null is not allowed</font>| <font color="#FF4500">Null is not allowed</font>| Dictionary| Thread-safe |
 | ConcurrentHashMap | <font color="#FF4500">Null is not allowed</font>| <font color="#FF4500">Null is not allowed</font>| AbstractMap| Segment lock |
 | TreeMap | <font color="red">Null is not allowed</font>| <font color="blue">Null is allowed</font>| AbstractMap| Thread-unsafe |
 | HashMap | <font color="blue">Null is allowed</font>| <font color="blue">Null is allowed</font>|  AbstractMap| Thread-unsafe |
 
> <font color="#FF4500">반례: </font>Confused by `HashMap`, lots of people think *null* is allowed in `ConcurrentHashMap`. Actually,  `NullPointerException` will be thrown when putting in *null* value.

14\. **[참조사항]** Properly use sort and order of a collection to avoid negative influence of unsorted and unordered one.  
> <font color="#977C00">Note: </font>*Sorted* means that its iteration follows  specific sorting rule. *Ordered* means the order of elements in each traverse is stable. e.g. `ArrayList` is ordered and unsorted, `HashMap` is unordered and unsorted, `TreeSet` is ordered and sorted.

15\. **[참조사항]** Deduplication operations could be performed quickly since set stores unique values only. Avoid using method *contains* of `List` to perform traverse, comparison and de-duplication.  


### <font color="green">Concurrency</font>
1\. **[필수]** Thread-safe should be ensured when initializing singleton instance, as well as all methods in it.
> <font color="#977C00">Note: </font>Resource driven class, utility class and singleton factory class are all included.

2\. **[필수]** A meaningful thread name is helpful to trace the error information, so assign a name when creating threads or thread pools.   
 > <font color="#019858">예시: </font>
 ```java
 public class TimerTaskThread extends Thread {
		public TimerTaskThread() {
			super.setName("TimerTaskThread"); 
		    … 
		}
 }
 ```  

3\. **[필수]** Threads should be provided by thread pools. Explicitly creating threads is not allowed. 
 > <font color="#977C00">Note: </font>Using thread pool can reduce the time of creating and destroying thread and save system resource. If we do not use thread pools, lots of similar threads will be created which lead to "running out of memory" or over-switching problems.

4\. **[필수]** A thread pool should be created by `ThreadPoolExecutor` rather than `Executors`. These would make the parameters of the thread pool understandable. It would also reduce the risk of running out of system resource.  
 > <font color="#977C00">Note: </font>Below are the problems created by usage of `Executors` for thread pool creation:   
&emsp;&emsp;1) `FixedThreadPool` and `SingleThreadPool`:  
&emsp;&emsp;Maximum request queue size `Integer.MAX_VALUE`. A large number of requests might cause OOM.   
&emsp;&emsp;2) `CachedThreadPool` and `ScheduledThreadPool`:  
&emsp;&emsp;The number of threads which are allowed to be created is `Integer.MAX_VALUE`. Creating too many threads might lead to OOM.

5\. **[필수]** `SimpleDateFormat` is unsafe, do not define it as a *static* variable. If have to, lock or `DateUtils` class must be used.  
 > <font color="#019858">예시: </font>Pay attention to thread-safety when using `DateUtils`. It is 추천 to use as below:
 ```java
private static final ThreadLocal<DateFormat> df = new ThreadLocal<DateFormat>() {  
    @Override  
    protected DateFormat initialValue() {  
        return new SimpleDateFormat("yyyy-MM-dd");  
    }  
};  
 ```
 > <font color="#977C00">Note: </font>In JDK8, `Instant` can be used to replace `Date`, `Calendar` is replaced by `LocalDateTime`, `Simpledateformatter` is replaced by `DateTimeFormatter`.
 
6\. **[필수]** `remove()` method must be implemented by `ThreadLocal` variables, especially when using thread pools in which threads are often reused. Otherwise, it may affect subsequent business logic and cause unexpected problems such as memory leak.    
> <font color="#019858">예시: </font>
```java
objectThreadLocal.set(someObject);
try {
    ...
} finally {
    objectThreadLocal.remove();
}
```

7\. **[필수]** In highly concurrent scenarios, performance of `Lock` should be considered in synchronous calls. A block lock is better than a method lock. An object lock is better than a class lock.

8\. **[필수]** When adding locks to multiple resources, tables in the database and objects at the same time, locking sequence should be kept consistent to avoid deadlock.    
> <font color="#977C00">Note: </font> If thread 1 does update after adding lock to table A, B, C accordingly, the lock sequence of thread 2 should also be A, B, C, otherwise deadlock might happen.

9\. **[필수]** A lock needs to be used to avoid update failure when modifying one record concurrently. Add lock either in application layer, in cache, or add optimistic lock in the database by using version as update stamp.  
 > <font color="#977C00">Note: </font>If access confliction probability is less than 20%, recommend to use optimistic lock, otherwise use pessimistic lock. Retry number of optimistic lock should be no less than 3.

10\. **[필수]** Run multiple `TimeTask` by using `ScheduledExecutorService` rather than `Timer` because `Timer` will kill all running threads in case of failing to catch exceptions.

11\. **[추천]** When using `CountDownLatch` to convert asynchronous operations to synchronous ones, each thread must call `countdown` method before quitting. Make sure to catch any exception during thread running, to let `countdown` method be  executed. If main thread cannot reach `await` method, program will return until timeout.  
> <font color="#977C00">Note: </font>Be careful, exception thrown by sub-thread cannot be caught by main thread.

12\. **[추천]** Avoid using `Random` instance by multiple threads. Although it is safe to share this instance, competition on the same seed will damage performance.  
> <font color="#977C00">Note: </font>`Random` instance includes instances of `java.util.Random` and `Math.random()`.  
> <font color="#019858">예시: </font>After JDK7, API `ThreadLocalRandom` can be used directly. But before JDK7, instance needs to be created in each thread.

13\. **[추천]** In concurrent scenarios, one easy solution to optimize the  lazy initialization problem by using double-checked locking  (referred to The Double-checked locking is broken Declaration), is to declare the object type as `volatile`.    
> <font color="#FF4500">반례: </font>
```java
class Foo { 
    private Helper helper = null;
    public Helper getHelper() {
        if (helper == null) {
            synchronized(this) {
                if (helper == null) 
                helper = new Helper();
            }   
        } 
        return helper;
    }
    // other functions and members...
}
```

14\. **[참조사항]** `volatile` is used to solve the problem of invisible memory in multiple threads. *Write-Once-Read-Many* can solve variable synchronization problem. But *Write-Many* cannot settle thread safe problem. For `count++`, use below example:　    
```java
AtomicInteger count = new AtomicInteger(); 
count.addAndGet(1); 
```  
> <font color="#977C00">Note: </font>In JDK8, `LongAdder` is 추천 which reduces retry times of optimistic lock and has better performance than `AtomicLong`.

15\. **[참조사항]** Resizing `HashMap` when its capacity is not enough might cause dead link and high CPU usage because of high-concurrency. Avoid this risk in development.  
 
16\. **[참조사항]** `ThreadLocal` cannot solve update problems of shared object. It is 추천 to use a *static* `ThreadLocal` object which is shared by all operations in the same thread. 

### <font color="green">Flow Control Statements</font>
1\. **[필수]** In a `switch` block, each case should be finished by *break/return*. If not, a note should be included to describe at which case it will stop. Within every `switch` block, a default statement must be present, even if it is empty.

2\. **[필수]** Braces are used with *if*, *else*, *for*, *do* and *while* statements, even if the body contains only a single statement. Avoid using the following example:
```java
    if (condition) statements; 
```

3\. **[추천]** Use `else` as less as possible, `if-else` statements could be replaced by:
```java
if (condition) {
    ...
    return obj;  
}  
// other logic codes in else could be moved here
```    
> <font color="#977C00">Note: </font> If statements like `if()...else if()...else...` have to be used to express the logic, **[필수]** nested conditional level should not be more than three.   
> <font color="#019858">예시: </font> `if-else` code with over three nested conditional levels can be replaced by *guard statements* or *State Design Pattern*. Example of *guard statement*:

```java
public void today() {
    if (isBusy()) {
        System.out.println("Change time.");
        return;
    }

    if (isFree()) {
        System.out.println("Go to travel.");
        return;
    }

    System.out.println("Stay at home to learn Alibaba Java Coding Guidelines.");
    return;
}
```

4\. **[추천]** Do not use complicated statements in conditional statements (except for frequently used methods like *getXxx/isXxx*). Use *boolean* variables to store results of complicated statements temporarily will increase the code's readability.  
> <font color="#977C00">Note: </font>Logic within many `if` statements are very complicated. Readers need to analyze the final results of the conditional expression to decide what statement will be executed in certain conditions.    
> <font color="#019858">예시: </font>
```java
// please refer to the pseudo-code as follows 
boolean existed = (file.open(fileName, "w") != null) && (...) || (...);
if (existed) {
    ...
}  
```  
 > <font color="#FF4500">반례: </font>  
```java
if ((file.open(fileName, "w") != null) && (...) || (...)) {
    ...
}
```

5\. **[추천]** Performance should be considered when loop statements are used. The following operations are better to be processed outside the loop statement, including object and variable declaration, database connection, `try-catch` statements.

6\. **[추천]** Size of input parameters should be checked, especially for batch operations.  

7\. **[참조사항]** Input parameters should be checked in following scenarios:     
&emsp;&emsp;1) Low-frequency implemented methods.  
&emsp;&emsp;2) Overhead of parameter checking could be ignored in long-time execution methods, but if illegal parameters lead to exception, the loss outweighs the gain. Therefore, parameter checking is still 추천 in long-time execution methods.  
&emsp;&emsp;3) Methods that needs extremely high stability or availability.    
&emsp;&emsp;4) Open API methods, including RPC/API/HTTP.  
&emsp;&emsp;5) Authority related methods.

8\. **[참조사항]** Cases that input parameters do not require validation:  
&emsp;&emsp;1) Methods very likely to be implemented in loops. A note should be included informing that parameter check should be done externally.   
&emsp;&emsp;2) Methods in bottom layers are very frequently called so generally do not need to be checked. e.g. If *DAO* layer and *Service* layer is deployed in the same server, parameter check in *DAO* layer can be omitted.    
&emsp;&emsp;3) *Private* methods that can only be implemented internally, if all parameters are checked or manageable.

### <font color="green">Code Comments</font>
1\. **[필수]** *Javadoc* should be used for classes, class variables and methods. The format should be '/\*\* comment \*\*/', rather than '// xxx'.   
> <font color="#977C00">Note: </font> In IDE, *Javadoc* can be seen directly when hovering, which is a good way to improve efficiency. 

2\. **[필수]** Abstract methods (including methods in interface) should be commented by *Javadoc*. *Javadoc* should include method instruction, description of parameters, return values and possible exceptions.  

3\. **[필수]** Every class should include information of author(s) and date.

4\. **[필수]** Single line comments in a method should be put above the code to be commented, by using `//` and multiple lines by using `/* */`. Alignment for comments should be noticed carefully.

5\. **[필수]** All enumeration type fields should be commented as *Javadoc* style.

6\. **[추천]** Local language can be used in comments if English cannot describe the problem properly. Keywords and proper nouns should be kept in English.  
 > <font color="#FF4500">반례: </font>To explain "TCP connection overtime" as "Transmission Control Protocol connection overtime" only makes it more difficult to understand.

7\. **[추천]** When code logic changes, comments need to be updated at the same time, especially for the changes of parameters, return value, exception and core logic.

8\. **[참조사항]** Notes need to be added when commenting out code.  
> <font color="#977C00">Note: </font> If the code is likely to be recovered later, a reasonable explanation needs to be added. If not, please delete directly because code history will be recorded by *svn* or *git*.

9\. **[참조사항]** Requirements for comments:   
&emsp;&emsp;1) Be able to represent design ideas and code logic accurately.   
&emsp;&emsp;2) Be able to represent business logic and help other programmers understand quickly. A large section of code without any comment is a disaster for readers. Comments are written for both oneself and other people. Design ideas can be quickly recalled even after a long time. Work can be quickly taken over by other people when needed.

10\. **[참조사항]** Proper naming and clear code structure are self-explanatory. Too many comments need to be avoided because it may cause too much work on updating if code logic changes. 
 > <font color="#FF4500">반례: </font>  
```java
// put elephant into fridge
put(elephant, fridge);  
```  
The name of method and parameters already represent what does the method do, so there is no need to add extra comments.

11\. **[참조사항]** Tags in comments (e.g. TODO, FIXME) need to contain author and time. Tags need to be handled and cleared in time by scanning frequently. Sometimes online breakdown is caused by these unhandled tags.    
&emsp;&emsp;1) TODO: TODO means the logic needs to be done, but not finished yet. Actually,  TODO is a member of *Javadoc*, although it is not realized in *Javadoc* yet, but has already been widely used. TODO can only be used in class, interface and methods, since it is a *Javadoc* tag.   
&emsp;&emsp;2) FIXME: FIXME is used to represent that the code logic is not correct or does not work, should be fixed in time.

### <font color="green">Other</font>
1\. **[필수]** When using regex, precompile needs to be done in order to increase the matching performance.  
> <font color="#977C00">Note: </font> Do not define `Pattern pattern = Pattern.compile(.);` within method body.

2\. **[필수]** When using attributes of POJO in velocity, use attribute names directly. Velocity engine will invoke `getXxx()` of POJO automatically. In terms of *boolean* attributes, velocity engine will invoke `isXxx()` (Do not use *is* as prefix when naming boolean attributes).  
> <font color="#977C00">Note: </font>For wrapper class `Boolean`, velocity engine will invoke `getXxx()` first.

3\. **[필수]** Variables must add exclamatory mark when passing to velocity engine from backend, like \$!{var}.  
 > <font color="#977C00">Note: </font>If attribute is *null* or does not exist, \${var} will be shown directly on web pages.

4\. **[필수]** The return type of `Math.random()` is double, value range is *0<=x<1* (<font color="blue">0</font> is possible). If a random integer is required, do not multiply x by 10 then round the result. The correct way is to use `nextInt` or `nextLong` method which belong to Random Object.

5\. **[필수]** Use `System.currentTimeMillis()` to get the current millisecond. Do not use `new Date().getTime()`. 
> <font color="#977C00">Note: </font>In order to get a more accurate time, use `System.nanoTime()`. In JDK8, use `Instant` class to deal with situations like time statistics.

6\. **[추천]** It is better not to contain variable declaration, logical symbols or any complicated logic in velocity template files.

7\. **[추천]** Size needs to be specified when initializing any data structure if possible, in order to avoid memory issues caused by unlimited growth.
 
8\. **[추천]** Codes or configuration that is noticed to be obsoleted should be resolutely removed from projects.   
> <font color="#977C00">Note: </font>Remove obsoleted codes or configuration in time to avoid code redundancy.  
 > <font color="#019858">예시: </font>For codes which are temporarily removed and likely to be reused, use **`///`** to add a reasonable note. 
```java
public static void hello() {
    /// Business is stopped temporarily by the owner.
    // Business business = new Business();
    // business.active();
    System.out.println("it's finished");
}
```