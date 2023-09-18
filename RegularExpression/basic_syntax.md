# basic syntax

`.`: wildcard

`+`: 1..⏦

`*`: 0..⏦

`?`: 0..1

`|`: or

`\u`: Unicode character by using hexadecimal representation

`[characher_group]`: any in characher_group

`[^characher_group]`: not in characher_group

`$`: at the end of the line

`^`: at the beginning of the line

`()`: make them a group

## example

```swift
// I wrote it only for self-help... 

func BasicWithRegex() -> String {
        let returnString : String
        let questionsFromGirlfriend = "到底為什麼不先講一聲"
        switch questionsFromGirlfriend {
        case let x where x.contains(/.*(\u9910\u5403)+[^\u55CE]*(\u597D)?(\u55CE)$/):
            // ..餐吃..(好)嗎
            returnString = "好啊"
        case let y where y.contains(/.*(\u4F60\u6703)+[^\u55CE]*(\u55CE)$/):
            // ..你會..嗎
            let yy = GetSubstring(words: y)
            returnString = "那\(yy)？"
        case let z where z.contains(/.*(\u662F\u4E0D\u662F)+.*/):
            // ..是不是..
            returnString = "那你是不是很喜歡我 >///<"
        case let a where a.contains(/.*(\u5230\u5E95\u70BA\u4EC0\u9EBC|\u70BA\u4EC0\u9EBC\u4E0D)+.*/):
            // ..到底為什麼.. || ..為什麼不..
            returnString = "我也不知道為什麼 Q^Q"
        case let b where b.contains(/.*(\u4F60\u5230\u5E95\u5728)+.*/):
            // ..你到底在..
            returnString = "對不起 orz"
        default:
            returnString = "你還是一樣漂亮！"
        }
        return returnString
    }

    // just put it here in case you wanna know...
    func GetSubstring(words : String) -> String {
        var substring = words
        
        while true {
            if substring[substring.startIndex] == "你" && substring[substring.index(after: substring.startIndex)] == "會" {
                return substring
            } else {
                substring.removeFirst(1)
            }
        }
    }
```

Since/If our/your native language is traditional Chinese, `BasicWithRegex()` can be rewritten as follows:

```swift
func RegexWithoutUnicode() -> String {
        let returnString : String
        let questionsFromGirlfriend = "餐吃嗎嗎"
        switch questionsFromGirlfriend {
        case let x where x.contains(/.*(餐吃)+[^嗎]*(好)?(嗎)$/):
            // ..餐吃..(好)嗎
            returnString = "好啊"
        case let y where y.contains(/.*(你會)+[^嗎]*(嗎)$/):
            // ..你會..嗎
            let yy = GetSubstring(words: y)
            returnString = "那\(yy)？"
        case let z where z.contains(/.*(是不是)+.*/):
            // ..是不是..
            returnString = "那你是不是很喜歡我 >///<"
        case let a where a.contains(/.*(到底為什麼|為什麼不)+.*/):
            // ..到底為什麼.. || ..為什麼不..
            returnString = "我也不知道為什麼 Q^Q"
        case let b where b.contains(/.*(你到底在)+.*/):
            // ..你到底在..
            returnString = "對不起 orz"
        default:
            returnString = "你還是一樣漂亮！"
        }
        return returnString
    }
```

## reference

#### easiler to understand than wiki
* Regular Expression Language - Quick Reference
    * https://learn.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference

#### get the Unicode of the specific Chinese character
* 全字庫
    * https://www.cns11643.gov.tw/searchQ.jsp?ID=0