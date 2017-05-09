��׿������ָ�ϲ�����Ϣ

��ǩ���ո�ָ����� CodeStyle Android

--- 
# һ�����

����ĵ��ο���[Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)�͹ٷ�[Android Code Style for Contributors](https://source.android.com/source/code-style.html) ������淶�����ĵ������ο���������ʽ����ʹ�� `AndroidStudio` Ĭ��ģ�弴�ɣ�ʹ�ø�ʽ����ݼ�`(ctrl+alt+L/commond+alt+L)`��`Eclipes(ctrl+shift+F)`�����������ϣ���

----

# ��������

## 1.Դ�ļ�����

### 1.1�ļ���

Դ�ļ�����������������������Сд���У��ļ���չ��Ϊ.java��

### 1.2 �ļ����룺UTF-8

Դ�ļ������ʽΪ`UTF-8`��

## 2.�����ַ�

### 2.1 ����ת������

���ھ�������ת�����е��κ��ַ�`(\b, \t, \n, \f, \r, \��, \����)`������ʹ������ת�����У���������Ӧ�İ˽���(����\012)��Unicode(����\u000a)ת�塣

### 2.2��ASCII�ַ�

����ʣ��ķ�ASCII�ַ�����ʹ��ʵ�ʵ�Unicode�ַ�(�����)������ʹ�õȼ۵�Unicodeת���(����\u221e)��ȡ�����ĸ����ô���������Ķ�����⡣

>Tip:��ʹ��Unicodeת�������һЩʵ�ʵ�Unicode�ַ�ʱ��������Щע�͸������ͣ��������ڱ����Ķ�����⡣
���磺
```java
//��õģ���ʹû��ע��Ҳ�ǳ�����
String unitAbbrev = "��s";  
//������û������Ҫ������
String unitAbbrev = "\u03bcs"; // "��s" 
//�������������Եñ�׾�����׳���
String unitAbbrev = "\u03bcs"; // Greek letter mu, "s"  
//���㣬���߸�������������ʲô
String unitAbbrev = "\u03bcs"; 
//Good�����ڷǴ�ӡ�ַ���ʹ��ת�壬���ڱ�Ҫʱд��ע��
return '\ufeff' + content; // byte order mark 
```
| Example | Discussion |
|---|---|
| String unitAbbrev = "��s"; | Best: perfectly clear even without a comment. |
| String unitAbbrev = "\u03bcs"; // "��s" |Allowed, but there's no reason to do this. |
| String unitAbbrev = "\u03bcs"; // Greek letter mu, "s" | Allowed, but awkward and prone to mistakes. |
| String unitAbbrev = "\u03bcs"; | Poor: the reader has no idea what this is. |
| return '\ufeff' + content; // byte order mark | Good: use escapes for non-printable characters, and comment if necessary. |

> Tip:��Զ��Ҫ���ں���ĳЩ��������޷���ȷ�����ASCII�ַ�������Ĵ���ɶ��Ա��������޷���ȷ�����ASCII�ַ�ʱ������Ȼ�޷���ȷ���У�
��ͻ�ȥfix��Щ������ˡ�

## 3.Դ�ļ��ṹ

> 1.���֤���Ȩ��Ϣ(������Ҫ)
> 2.package���
> 3.import���
> 4.������

> Tip:ÿ������֮����һ�����и�����


### 3.1 ���֤���Ȩ��Ϣ

���һ���ļ��������֤���Ȩ��Ϣ����ô��Ӧ���������ļ���ǰ�档

### 3.2 package���

package ��䲻���У�������(4.4��)����������package��䡣(��package���д��һ����)

### 3.3 import���

#### 3.3.1 import��Ҫʹ��ͨ���

������Ҫ��������������import��䣺import java.util.*;

#### 3.3.2 ��Ҫ����

import��䲻���У������Ʋ���������import��䡣

#### 3.3.3 ˳��ͼ��

import���ɷ�Ϊ���¼��飬�������˳��ÿ����һ�����зָ���

���еľ�̬�����������
com.google imports(�������Դ�ļ�����com.google����)
�������İ���ÿ��������Ϊһ�飬�ֵ������磺android, com, junit, org, sun
java imports5.javax imports���ڲ����У����ֵ������С�
> ע��Android Studio���Զ����������

### 3.4 ������

#### 3.4.1 ֻ��һ������

������ÿ�������඼��һ������ͬ����Դ�ļ���(��Ȼ��������.java��׺)��
���⣺package-info.java�����ļ��п�û��package-info�ࡣ

#### 3.4.2 ���Ա˳��

��ĳ�Ա˳�����ѧ���кܴ��Ӱ�죬����Ҳ������Ψһ��ͨ�÷��򡣲�ͬ����Գ�Ա����������ǲ�ͬ�ġ�

����Ҫ��һ�㣬ÿ����Ӧ����ĳ���߼�ȥ�������ĳ�Ա��ά����Ӧ��Ҫ�ܽ������������߼������磬 �µķ�����������ϰ���Ե���ӵ���Ľ�β����Ϊ�������ǰ�ʱ��˳�����ĳ���߼�������ġ�

##### 3.4.2.1 ���黮��

�����ļ���������

> ����������
UI�ؼ���Ա����������
��ͨ��Ա����������
��ʼ����ط�����
���ص��߼�������
��ͨ�߼�������
�ڲ���������

##### 3.4.2.2 ��Ҫ�����ط�������

��һ�����ж�����캯�������Ƕ��ͬ����������Щ����/����Ӧ�ð�˳�������һ���м䲻Ҫ�Ž���������/������

## 4. ��ʽ����

˵������״�ṹ(block-like construct)ָ����һ���࣬�������캯�������塣��Ҫע����ǣ������ʼ���еĳ�ʼֵ�ɱ�ѡ���Ե���Ϊ��״�ṹ(4.8.3.1��)��

### 4.1 ������

#### 4.1.1 ʹ�ô�����

��������if, else, for, do, while���һ��ʹ�ã���ʹֻ��һ�����(���ǿ�)��ҲӦ�ðѴ�����д�ϡ�

#### 4.1.2 �ǿտ飺K & R ���

���ڷǿտ�Ϳ�״�ṹ����������ѭ Kernighan �� Ritchie ��� (Egyptian brackets):

> �������ǰ������
������ź���
�Ҵ�����ǰ����
����Ҵ�������һ����䡢������������ֹ�����Ҵ����ź���; ���򲻻��С�
���磬����Ҵ����ź�����else�򶺺ţ��򲻻��С�

ʾ����
```java
return () -> {
  while (condition()) {
    method();
  }
};

return new MyClass() {
  @Override public void method() {
    if (condition()) {
      try {
        something();
      } catch (ProblemException e) {
        recover();
      }
    } else if (otherCondition()) {
      somethingElse();
    } else {
      lastThing();
    }
  }
};
```
> Tip:enum���һЩ���⡣

#### 4.1.3 �տ飺�����ü��汾

һ���յĿ�״�ṹ��ʲôҲ�������������ſ��Լ���д��{}������Ҫ���С�

���⣺�������һ���������һ����(if/else �� try/catch/finally) ����ʹ��������û���ݣ��Ҵ�����ҲҪ���С�
ʾ����
```java
 //���ǿ��Խ��ܵ�
 void doNothing() {}

 // ��Ҳ���Խ���
 void doNothingElse() {
  }
 // �����ͽ��ܲ�����
 try {
    doSomething();
 } catch (Exception e) {}
```
### 4.2 ��������4���ո�

ÿ����ʼһ���µĿ飬��������4���ո񣬵������ʱ������������ǰ�����������������������ڴ����ע�͡�

### 4.3 һ��һ�����

ÿ������Ҫ���С�

### 4.4 �����ƣ�80��100

һ����Ŀ����ѡ��һ��80���ַ���100���ַ��������ƣ������������⣬�κ�һ�������������ַ������ƣ������Զ����С�

���⣺
> 1.���������������Ƶ���(���磬Javadoc�е�һ����URL������һ������JSNI�����ο�)��
> 2.package��import���
> 3.ע������Щ���ܱ����в�ճ����shell�е������С�

### 4.5 �Զ�����

����˵����һ������£�һ�г�����Ϊ�˱��ⳬ��������(80��100���ַ�)������Ϊ���У����ǳ�֮Ϊ�Զ�����(line-wrapping)�����ǲ�û��ȫ�棬ȷ���Ե�׼����������ÿһ�����������Զ����С��ܶ�ʱ�򣬶���ͬһ�δ�����кü�����Ч���Զ����з�ʽ��

> Tip:��ȡ������ֲ����������ڲ����е�����½���������������

#### 4.5.1 ������Ͽ�

�Զ����еĻ���׼���ǣ����������ڸ��ߵ��﷨���𴦶Ͽ���

    1.����ڷǸ�ֵ��������Ͽ�����ô�ڸ÷���ǰ�Ͽ�(����+������λ����һ��)��
      ע�⣺��һ���� Google �������Եı�̷��ͬ(�� C++ �� JavaScript )�� ��������Ҳ���������¡�������������ţ���ָ���(.)�����ͽ����е�             &��)��catch ���еĹܵ�����(catch (FooException | BarException e)

    2.����ڸ�ֵ��������Ͽ���ͨ�����������ڸ÷��ź�Ͽ�(����=������ǰ�����������ͬһ��)����������Ҳ������foreach����еķֺš�
    
    3.���������캯����������������ͬһ�С�
    
    4.����(,)����ǰ�����������ͬһ�С�

#### 4.5.2 �Զ�����ʱ��������+8���ո�

�Զ�����ʱ����һ�к��ÿһ�����ٱȵ�һ�ж�����8���ո�(ע�⣺�Ʊ����������������2.3.1��)�������������Զ�����ʱ���������ܻ��������ֻ8���ո�(�﷨Ԫ�ش��ڶ༶ʱ)��һ����ԣ�����������ʹ����ͬ���������ҽ������ǿ�ʼ��ͬ���﷨Ԫ�ء�

> **Note:** 4.6.3ˮƽ����һ����ָ����������ʹ�ÿɱ���Ŀ�Ŀո�������ǰ���еķ��š�

### 4.6 �հ�

#### 4.6.1 ��ֱ�հ�

���������Ҫʹ��һ�����У�

    1.���������ĳ�Ա֮�䣺�ֶΣ����캯����������Ƕ���࣬��̬��ʼ���飬ʵ����ʼ���顣 ���⣺ ���������ֶ�֮��Ŀ����ǿ�ѡ�ģ������ֶεĿ�����Ҫ�������ֶν����߼����顣
    
    2.�ں������ڣ������߼������ʹ�ÿ��С�
    
    3.���ڵĵ�һ����Աǰ�����һ����Ա��Ŀ����ǿ�ѡ��(�Ȳ�����Ҳ���������������Ӹ���ϲ�ö���)��
    
    4.Ҫ���㱾�ĵ��������ڵĿ���Ҫ��(����3.3�ڣ�import���)
��������Ŀ���������ģ���û�б�Ҫ������(����Ҳ������������)��

#### 4.6.2 ˮƽ�հ�

��������������������򣬲��ҳ������֣�ע�ͺ�Javadoc�õ������ո񣬵���ASCII�ո�Ҳ���������¼����ط���

    1.�ָ��κα��������������������(()(��if, for catch��)��
    
    2.�ָ��κα���������ǰ����Ҵ�����(})(��else, catch)��
    
    3.���κ��������ǰ({)���������⣺
        o @SomeAnnotation({a, b})(��ʹ�ÿո�)��
        o String[][] x = foo;(�����ż�û�пո񣬼������Note)��
    4.���κζ�Ԫ����Ԫ����������ࡣ��Ҳ���������¡�������������ţ�
        o ���ͽ����е�&()��
        o catch���еĹܵ�����(catch (FooException | BarException e)��
        o foreach����еķֺš�
    5.��, : ;��������())��
    
    6.�����һ��������ע�ͣ���˫б��(//)���߶�Ҫ�ո���������������ո񣬵�û�б�Ҫ��
    
    7.���ͺͱ���֮�䣺List list��
    
    8.�����ʼ���У��������ڵĿո��ǿ�ѡ�ģ���new int[] {5, 6}��new int[] { 5, 6 }���ǿ��Եġ�
    
> **Note��** ������򲢲�Ҫ����ֹһ�еĿ��ػ��β��Ҫ����Ŀո�ֻ���ڲ��ո���Ҫ��

#### 4.6.3 ˮƽ���룺����Ҫ��

����˵����ˮƽ����ָ����ͨ�����ӿɱ������Ŀո���ʹĳһ�е��ַ�����һ�е���Ӧ�ַ����롣
��������ģ���Google��̷��Դ˲���Ҫ�󡣼�ʹ�����Ѿ�ʹ��ˮƽ����Ĵ��룬����Ҳ����Ҫȥ�������ַ��

����ʾ����չʾδ����Ĵ��룬Ȼ���Ƕ���Ĵ��룺
```java
private int x; // this is fine
private Color color; // this too

private int    x;         // permitted, but future edits
private Color  color;     // may leave it unaligned
```
> **Tip:**  ��������Ӵ���ɶ��ԣ�����Ϊ�պ��ά���������⡣

### 4.7 ��С�������޶��飺�Ƽ�

�������ߺ�reviewer����Ϊȥ��С����Ҳ����ʹ���뱻��⣬����ȥ��С�������ô���������Ķ����������ǲ�Ӧ��ȥ��С���š�

### 4.8 ����ṹ

#### 4.8.1 ö����

ö�ٳ������ö��Ÿ��������п�ѡ��
```java
private enum Answer {
  YES {
    @Override public String toString() {
      return "yes";
    }
  },

  NO,
  MAYBE
}
```

û�з������ĵ���ö�����д�������ʼ���ĸ�ʽ��
```java
private enum Suit { CLUBS, HEARTS, SPADES, DIAMONDS }
```
����ö����Ҳ��һ���࣬�������������������ĸ�ʽ����Ҳ������ö���ࡣ

#### 4.8.2 ��������

##### 4.8.2.1 ÿ��ֻ����һ������

��Ҫʹ���������������`int a, b`;��

##### 4.8.2.2 ��Ҫʱ����������������г�ʼ��

��Ҫ��һ�������Ŀ�ͷ�Ѿֲ�����һ���Զ�������(����c���Ե�����)�������ڵ�һ����Ҫʹ����ʱ�������� �ֲ�����������ʱ��þͽ��г�ʼ�������������󾡿���г�ʼ����

#### 4.8.3 ����

##### 4.8.3.1 �����ʼ������д�ɿ�״�ṹ

�����ʼ������д�ɿ�״�ṹ�����磬�����д������OK�ģ�
```java
new int[] {
        0, 1, 2, 3 
}
new int[] {
        0,
        1,
        2,
        3
}
new int[] {
        0, 1,
        2, 3
}
new int[]
        {0, 1, 2, 3}
```
##### 4.8.3.2 ��C������������

�����������͵�һ���֣�`String[] args`�� ����` String args[]`��

#### 4.8.4 switch���

����˵����switch��Ĵ���������һ����������顣
ÿ����������һ������switch��ǩ`(case FOO:��default:)`���������һ���������䡣

##### 4.8.4.1 ����

��������״�ṹһ�£�switch���е���������Ϊ2���ո�ÿ��switch��ǩ������һ�У�������2���ո�д��һ���������䡣

##### 4.8.4.2 Fall-through��ע��

��һ��`switch`���ڣ�ÿ�������Ҫôͨ��`break, continue, return`���׳��쳣����ֹ��Ҫôͨ��һ��ע����˵�����򽫼���ִ�е���һ������飬 �κ��ܱ�������˼��ע�Ͷ���OK��(���͵�����// fall through)����������ע�Ͳ�����Ҫ�����һ�������(һ����default)�г��֡�

ʾ����
```java
switch (input) {
    case 1:
    case 2:
        prepareOneOrTwo();        // fall through
    case 3:
        handleOneTwoOrThree();
        break;
    default:
        handleLargeNumber(input);
}
```
##### 4.8.4.3 default�����Ҫд����

ÿ��switch��䶼����һ��`default`����飬��ʹ��ʲô����Ҳ��������

#### 4.8.5 ע��(Annotations)

ע��������ĵ�����棬Ӧ�����ࡢ�����͹��캯����һ��ע���ռһ�С���Щ���в������Զ����У�����������𲻱䡣

���磺
```java
@Override
@Nullable
public String getNameIfPresent() { ... }
```
���⣺������ע����Ժ�ǩ���ĵ�һ�г�����ͬһ�С�
���磺
```java
@Override public int hashCode() { �� }
```
Ӧ�����ֶε�ע������ĵ�����֣�Ӧ�����ֶεĶ��ע���������ֶγ�����ͬһ�С�
���磺
```java
@Partial @Mock DataLoader loader;
```
�����;ֲ�����ע��û���ض�����

#### 4.8.6 ע��

##### 4.8.6.1 ��ע�ͷ��

��ע��������Χ�Ĵ�����ͬһ�����������ǿ�����`/*��*/`���Ҳ������`// ��`��񡣶��ڶ��е�`/*��*/`ע�ͣ������б���ӿ�ʼ�� ������ǰһ�еĶ��롣
```java
/*
 * This is          // And so           /* Or you can
 * okay.            // is this.          * even do this. */
 */
```
ע�Ͳ�Ҫ��������ǺŻ������ַ����ƵĿ���

> **Tip:**  ��д����ע��ʱ�������ϣ���ڱ�Ҫʱ�����»���(��ע���������һ��)����ôʹ��/*��*/��

#### 4.8.7 ����������Ʒ�

�����ͳ�Ա���ڶ�����Ʒ�����Java���Թ淶���Ƽ���˳����֡�
`
public protected private abstract static final transient Volatile synchronized native strictfp
`
## 5. ����Լ��

### 5.1 �����б�ʶ����ͨ�õĹ���

��ʶ��ֻ��ʹ��ASCII��ĸ�����֣����ÿ����Ч�ı�ʶ�����ƶ���ƥ��������ʽ\w+��

### 5.2 ��ʶ�����͵Ĺ���

#### 5.2.1 ����

����ȫ��Сд�������ĵ���ֻ�Ǽ򵥵�������������ʹ���»��ߡ�
���÷�������������ȫ��ʹ��Сд��ĸ��һ������Ϊcom����������Ϊxx�������ǹ�˾������˵���㣩��������������Ӧ�ý����������ļ�����Ϊģ������㼶����

���磺`com.zhiyicx.thinksns.ui`
#### 5.2.2 ����

��������`���շ�(UpperCamelCase)`����д��

����ͨ�������ʻ����ʶ���ӿ�������ʱ���������ݴʻ����ݴʶ�����ڻ�û���ض��Ĺ������֮��Ч��Լ��������ע�����͡�

���ʣ����ô��շ�������������������д�����Ǹ���д��������֪�ģ� ����HTML,URL������������а���������д���򵥴���д��ÿ����ĸ��Ӧ��д��

|��|	����|	����|
|:---:|:---:|:---:|
|Activity ��|	ActivityΪ��׺��ʶ|	��ӭҳ����WelcomeActivity|
|Adapter��|	Adapter Ϊ��׺��ʶ|	�������������� NewDetailAdapter|
|������	|ParserΪ��׺��ʶ|	��ҳ������HomePosterParser|
|���߷�����|	Utils��ManagerΪ��׺��ʶ|	�̳߳ع����ࣺThreadPoolManager��־�����ࣺLogUtils��ӡ�����ࣺPrinterUtils|
|���ݿ���|	��DBHelper��׺��ʶ|	�������ݿ⣺NewDBHelper|
|Service��	|��ServiceΪ��׺��ʶ|	ʱ�����TimeService|
|Receive��	|��ReceiverΪ��׺��ʶ|	���ͽ���JPushReceiver|
|ContentProvider	|��ProviderΪ��׺��ʶ	||
|���������|	��Base��ͷ|	BaseActivity,BaseFragment|
|������|��Ҫ���Ե�������ƿ�ʼ����Test������|HashTest �� HashIntegrationTest|
|�ӿڣ�interface��|�ӿ�������������һ�����ô��շ�������������I��ͷ����able��ible��er��β|interface ILoginView; interface Runnable ;interface Accessible;interface OnclickListener|
> ע�⣺
�����Ŀ����MVP������Model��View��Presenter�Ľӿڶ���IΪǰ׺�����Ӻ�׺��

#### 5.2.3 ������

���������� `С�շ�(LowerCamelCase)` ����д��

������ͨ���Ƕ��ʻ򶯴ʶ��

| ����	| ˵�� |
|:---:|:---:|
|initXX()|	��ʼ����ط���,ʹ��initΪǰ׺��ʶ�����ʼ������initView()|
|isXX() checkXX()|	��������ֵΪboolean�͵���ʹ��is��checkΪǰ׺��ʶ|
|getXX()|	����ĳ��ֵ�ķ�����ʹ��getΪǰ׺��ʶ|
|handleXX()|	�����ݽ��д���ķ���������ʹ��handleΪǰ׺��ʶ|
|displayXX()/showXX()|	������ʾ�����ʾ��Ϣ��ʹ��display/showΪǰ׺��ʶ|
|saveXX()|	�뱣��������صģ�ʹ��saveΪǰ׺��ʶ|
|resetXX()|	����������ģ�ʹ��resetǰ׺��ʶ|
|clearXX()|	���������ص�|
|removeXXX()|	���������ص�|
|drawXXX()	|�������ݻ�Ч����صģ�ʹ��drawǰ׺��ʶ|


�»��߿��ܳ�����JUnit���Է������������Էָ����Ƶ��߼������һ�����͵�ģʽ�ǣ�test_������testPop_emptyStack��

��������Ψһ��ȷ�ķ�ʽ���������Է�����

#### 5.2.4 ������

����������ģʽΪCONSTANT_CASE��ȫ����ĸ��д�����»��߷ָ����ʡ���Щ����ͨ�������ʻ����ʶ���.
```java
// Constants
static final int NUMBER = 5;
static final ImmutableListNAMES = ImmutableList.of("Ed", "Ann");
static final Joiner COMMA_JOINER = Joiner.on(','); // because Joiner is immutable
static final SomeMutableType[] EMPTY_ARRAY = {};
enum SomeEnum { ENUM_CONSTANT }
// Not constants
static String nonFinal = "non-final";
final String nonStatic = "non-static";
static final SetmutableCollection = new HashSet();
static final ImmutableSetmutableElements = ImmutableSet.of(mutable);
static final Logger logger = Logger.getLogger(MyClass.getName());
static final String[] nonEmptyArray = {"these", "can", "change"};
```

#### 5.2.5 �ǳ����ֶ���

�ǳ����ֶ�����`LowerCamelCase`���Ļ����ϸ���Ϊ���·��

�����ṹΪscopeVariableNameType��

> scope����Χ

> �ǹ��У��Ǿ�̬�ֶ�������m��ͷ��

> ���зǾ�̬�ֶ�������p��ͷ��

> ��̬�ֶ�������s��ͷ��

> ���о�̬�ֶΣ�ȫ�ֱ�����������g��ͷ��

> public static final �ֶ�(����) ȫ����д�������»�����������

���ӣ�
```java
public class MyClass {  
       public static final int SOME_CONSTANT = 42;  
       public int pField;  
       private static MyClass sSingleton;  
       int mPackagePrivate;  
       private int mPrivate;  
       protected int mProtected; 
       public static int gField; 
}
```
> **Note:** ʹ��1�ַ�ǰ׺����ʾ���÷�Χ��1���ַ���ǰ׺����Сд��ǰ׺�������ɱ�����ǿ��һ�����ʻ���������ɵ����֣�����ÿ�����ʵ���д��ĸ��д��������ĸСд��������֤�˶Ա������ܹ�������ȷ�ĶϾ䡣

Type������

���ǵ�Android��ʹ�úܶ�UI�ؼ���Ϊ����ؼ�����ͨ��Ա���������Լ����ô��⣬����������ʾ�ؼ��ĳ�Ա����ͳһ���Ͽؼ���д��Ϊ��׺����ĩ������д����

������ͨ����һ�㲻������ͺ�׺�����ͳһ������ͺ�׺����ο���ĩ����д��

��ͳһ������ͨ���ڽ�β������һ�����ʣ��Ϳɴ�������ͳһ�ı��������Ǹ�������⣬Ҳ������������

> **Note��** �����Ŀ��ʹ��ButterKnife�������mǰ׺����LowerCamelCase���������
���磬��ʹ�� mCustomerStrFirst �� mCustomerStrLast������Ҫʹ��mFirstCustomerStr��mLastCustomerStr��


˵����

����������º�׺��List��Map��Set

����������º�׺��Arr

> **Note��** ���е�VO��ֵ����ͳһ���ñ�׼��lowerCamelCase����д�����е�DTO�����ݴ�����󣩾Ͱ��սӿ��ĵ��ж�����ֶ�����д��

#### 5.2.6 ������

��������LowerCamelCase����д

#### 5.2.7 �ֲ�������

�ֲ���������LowerCamelCase����д�������������͵����ƣ��ֲ������������и�Ϊ���ɵ���д��

��Ȼ��д�����ɣ�������Ҫ�����õ��ַ�����������������ʱ������ѭ��������

��ʹ�ֲ�������final�Ͳ��ɸı�ģ�Ҳ��Ӧ�ð���ʾΪ��������ȻҲ�����ó����Ĺ���ȥ��������

��ʱ����

��ʱ����ͨ����ȡ��Ϊi��j��k��m��n������һ���������ͣ�c��d��e������һ�������ַ��͡� �磺 for (int i = 0; i < len ; i++)���������͵�һ�����ʼ�û�пո�

#### 5.2.8 ���ͱ�����

���ͱ��������������ַ��֮һ����������

�����Ĵ�д��ĸ��������Ը�һ������(�磺E, T, X, T2)��
����������ʽ(5.2.2��)������Ӹ���д��T(�磺RequestT, FooBarT)��
#### 5.2.9 ��Դ�ļ������淶

##### 5.2.9.1. ��Դ�����ļ���XML�ļ���layout�����ļ�������

ȫ��Сд�������»�����������ʹ�����ʻ����ʴ��顣

    1) contentview ����
    ����Activity��Fragment��contentView��������������Ӧ����Ӧ����Ϊ��
    ��������ĸ��תΪСд�������ͺ͹��ܵ�����Ҳ���Ǻ�׺��ǰ׺����
    ���磺`activity_main.xml`
    
    2) Dialog������dialog_����.xml
    ���磺`dialog_hint.xml`
    
    3) PopupWindow������ppw_����.xml
    ���磺`ppw_info.xml`
    
    4) �б���������item_����.xml
    ���磺`item_city.xml`
    
    5) ������������ģ��_(λ��)����.xml
    ���磺 `include_head.xml��include_bottom.xml��include_title.xml`

##### 5.2.9.2. ��Դ�ļ���ͼƬdrawable�ļ����£���
ȫ��Сд�������»�������������ǰ׺����
> ����ģʽ���ɼӺ�׺ _small ��ʾСͼ, _big��ʾ��ͼ���߼����ƿ��ɶ�����ʼ��»�����ɣ��������¹���
��;_ģ����_�߼�����
��;_ģ����_��ɫ
��;_�߼�����
��;_��ɫ
˵������;Ҳָ�ؼ����ͣ������UI�ؼ���д��
���磺
`btn_main_home.png ����
divider_maket_white.png �ָ���
ic_edit.png ͼ��
bg_main.png ����
btn_red.png ��ɫ����
btn_red_big.png ��ɫ�󰴼�
ic_head_small.png Сͷ��
bg_input.png ����򱳾�
divider_white.png ��ɫ�ָ���
//����ж�����̬�簴ť�ȳ����� btn_xx.xml��selector��
`

|����	|����|
|:----:|:----:|
|btn_xx	|��ťͼƬʹ��btn_����Ч����selector��|
|btn_xx_normal	|��ťͼƬʹ��btn_�������Ч��|
|btn_xx_pressed	|��ťͼƬʹ��btn_���ʱ��Ч��|
|btn_xx_focused	|state_focused�۽�Ч��|
|btn_xx_disabled	|state_enabled (false)������Ч��|
|btn_xx_checked|	state_checkedѡ��Ч��|
|btn_xx_selected	|state_selectedѡ��Ч��|
|btn_xx_hovered	|state_hovered��ͣЧ��|
|btn_xx_checkable	|state_checkable��ѡЧ��|
|btn_xx_activated	|state_activated�����|
|btn_xx_windowfocused	|state_window_focused|
|bg_head	|����ͼƬʹ��bg_����_˵��|
|def_search_cell	|Ĭ��ͼƬʹ��def_����_˵��|
|ic_more_help	|ͼ��ͼƬʹ��ic_����_˵��|
|seg_list_line	|���зָ�������ͼƬʹ��seg_����_˵��|
|sel_ok 	|ѡ��ͼ��ʹ��sel_����_˵��|


##### 5.2.9.3. �����ļ���anim�ļ����£���

ȫ��Сд�������»�������������ǰ׺���֡�
> ���嶯���������¹���
> ģ����_�߼�����
> �߼�����
`refresh_progress.xml
market_cart_add.xml
market_cart_remove.xml
`
��ͨ��tween�����������±���е�������ʽ
// ǰ��Ϊ���������ͣ�����Ϊ����

|������������|	�淶д��|
|:---:|:---:|
|fade_in|	����|
|fade_out|	����|
|push_down_in|	���·�����|
|push_down_out	|���·��Ƴ�|
|push_left|	������|
|slide_in_from_top|	��ͷ����������|
|zoom_enter|	���ν���|
|slide_in|	��������|
|shrink_to_middle	|�м���С|

##### 5.2.9.4. values��name����

|���	|����|	ʾ��|
|:---:|:---:|:---:|
|strings|	strings��name����ʹ���»������������������¹���ģ����+�߼�����|	main_menu_about ���˵���������,friend_title ����ģ�������,friend_dialog_del ����ɾ����ʾ,login_check_email��¼��֤,dialog_title ���������,button_ok ȷ�ϼ� loading ��������|
|colors	| colors��name����ʹ���»������������������¹���ģ����+�߼����� ��ɫ|	friend_info_bg, friend_bg ,transparent ,gray|
|styles|	styles��name����ʹ�� Camel���������������¹���ģ����+�߼�����|	main_tabBottom|


##### 5.2.9.5. layout�е�id����
����ģʽΪ��view��д_view���߼�����
 ��д����׺���磺`tv_username��չʾ�û�����TextView��`

##### 5.2.9.6. ���ʵ��

    1) @Override����������
    
    ֻҪ�ǺϷ��ģ��Ͱ�@Overrideע������ϡ����Ǹ���ʹ����@Deprecated
    
    2) ������쳣�����ܺ���
    
    ������������ӣ��Բ�����쳣������Ӧ�Ǽ�����ȷ�ġ�(���͵���Ӧ��ʽ�Ǵ�ӡ��־���������������Ϊ�ǲ����ܵģ����������һ�� AssertionError �����׳���)

    3) ��̬��Ա��ʹ������е���
    
    ʹ���������þ�̬�����Ա�������Ǿ���ĳ���������ʽ��
    ```java
    Foo aFoo = ...;
    Foo.aStaticMethod(); // good
    aFoo.aStaticMethod(); // bad
    somethingThatYieldsAFoo().aStaticMethod(); // very bad
    ```
    4) Finalizers: ����
    
    ���ٻ�ȥ����Object.finalize��

�����ȷʵ�ǲ���Ҫ��catch�������κ���Ӧ����Ҫ��ע�ͼ���˵��(�����������)��
```java
try {
    int i = Integer.parseInt(response);
    return handleNumericResponse();
} catch (NumberFormatException ok) {
    // it's not numeric; that's fine, just continue
}
return handleTextResponse(response);
```
���⣺��ȷ�������Եķ������׳�һ�������е��쳣ʱ����û�б�Ҫ��ע�͡�
```java
try {
    emptyStack.pop();
    fail();
} catch (NoSuchElementException expected) {
}
```
> **Tip:**  ��������ʹ��finalize��������Ҫʹ������������ϸ�Ķ������Effective Java ��7�����Avoid Finalizers����

-----
## 7. Javadoc

### 7.1 ��ʽ

#### 7.1.1 һ����ʽ

Javadoc��Ļ�����ʽ������ʾ��
```java
/**
* Multiple lines of Javadoc text are written here,
* wrapped normally...
*/
 public int method(String p1) { ... }
```
���������µ�����ʽ��
```java
/** An especially short bit of Javadoc. */
```
������Javadoc����������һ��ʱ(��û��Javadoc���@XXX)������ʹ�õ�����ʽ��

#### 7.1.2 ����

����(����ֻ����������Ǻŵ���)������ڶ���֮���Javadoc���(@XXX)֮ǰ(����еĻ�)��

���˵�һ�����䣬ÿ�������һ������ǰ���б�ǩ<p>���������͵�һ�����ʼ�û�пո�

#### 7.1.3 Javadoc���

��׼��Javadoc��ǰ�����˳����֣�`@param, @return, @throws, @deprecated`,
ǰ����4�ֱ��������֣�����������Ϊ�ա� �������޷���һ�������ɣ���������Ҫ����������4���ո�

### 7.2 ժҪƬ��

ÿ������Ա��Javadoc��һ����̵�ժҪƬ�ο�ʼ�����Ƭ���Ƿǳ���Ҫ�ģ���ĳЩ����£�����Ψһ���ֵ��ı�����������ͷ��������С�

��ֻ��һ��СƬ�Σ�������һ�����ʶ���򶯴ʶ��������һ�������ľ��ӡ��������� ` A {@code Foo} is a����This method returns�� `��ͷ,��Ҳ������һ����������ʹ�䣬�� `Save the record��`��Ȼ�������ڿ�ͷ��д�������˱�㣬�������������Ǹ������ľ��ӡ�

> **Tip:**  
һ�������Ĵ����ǰѼ򵥵�Javadocд��
/** @return the customer ID */�����ǲ���ȷ�ġ���Ӧ��д��/** Returns the customer ID. */��

### 7.3 ������Ҫʹ��Javadoc

������ÿ��public�༰����ÿ��public��protected��Ա��ʹ��Javadoc��������һЩ���⣺

#### 7.3.1 ���⣺���������ķ���

���ڼ����Եķ�����getFoo��Javadoc�ǿ�ѡ��(�����ǿ��Բ�д��)����������³���д��Returns the foo����ȷʵҲû��ʲôֵ��д�ˡ�

��Ԫ�������еĲ��Է��������ǲ�����������������ˣ�����ͨ�����Դ���Щ������������������֪�����Ǹ�ʲô�ģ���˲���Ҫ������ĵ�˵����

> **Tip:**  
�����һЩ�����Ϣ����Ҫ�����˽�ģ���ô���ϵ����ⲻӦ��Ϊ������Щ��Ϣ�����ɡ����磬���ڷ�����`getCanonicalName`��
�Ͳ�Ӧ�ú����ĵ�˵������Ϊ���ߺܿ��ܲ�֪������`canonical name`ָ����ʲô��

#### 7.3.2 ���⣺����

���һ�����������˳����еķ�������ôJavadoc���Ǳ���ġ�

#### 7.3.3 ��ѡ��Javadoc

���ڰ��ⲻ�ɼ�����ͷ�����������Ҫ��Ҳ��Ҫʹ��Javadoc�ġ����һ��ע������������һ���࣬�������ֶε�����Ŀ�Ļ���Ϊ����ô���ע��Ӧ��д��Javadoc��������ͳһ���Ѻá�


-----
## ������¼
��1 UI�ؼ���д��

|�ؼ�	|��д	|����|
|:----:|:----:|:----:|
|LinearLayout   |	ll|	llFriend����mFriendLL|
|RelativeLayout	|rl	|rlMessage��mMessageRL|
|FrameLayout|	fl|	flCart��mCartFL|
|TableLayout|	tl|	tlTab��mTabTL|
|Button|	btn|	btnHome��mHomeBtn|
|ImageButton|	ibtn|	btnPlay��mPlayIBtn|
|TextView	|tv	|tvName��mNameTV|
|EditText|	et|	etName��mNameET|
|ListView|	lv|	lvCart��mCartLV|
|ImageView	|iv|	ivHead��mHeadIV|
|GridView|	gv	|gvPhoto��mPhotoGV|
��2 ������Ӣ�ĵ�����д:

|����|	��д|
|:---:|:---:|
|icon|	ic ����Ҫ����app��ͼ�꣩|
|color	|cl����Ҫ������ɫֵ��|
|divider|	di����Ҫ���ڷָ��ߣ���������Listview�е�divider����������ͨ�����е��ߣ�|
|selector	|sl����Ҫ����ĳһview����״̬����������Listview�е�selector����������ť��selector��|
|average|	avg|
|background|	bg����Ҫ���ڲ��ֺ��Ӳ��ֵı�����|
|buffer	|buf|
|control|	ctrl|
|delete	|del|
|document	|doc|
|error|	err|
|escape|	esc|
|increment	|inc|
|infomation	|info|
|initial|	init|
|image	|img|
|Internationalization|	I18N|
|length	|len|
|library|	lib|
|message|	msg|
|password|	pwd|
|position|	pos|
|server|	srv|
|string	|str|
|temp|	tmp|
|window	|wnd(win)|
> **Note:** ������ʹ�õ�����дԭ�򣺲�Ҫ����д�����Ǹ���д�ǹ��ϵġ�