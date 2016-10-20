This is a UWP class library to inject HTML into a RichTextBlock easily

**Usage:** 

1) In a XAML file, declare the namespace:

```xaml
xmlns:html="using:XAMLHtml" 
```

2) In RichTextBlock controls, set or databind the Html property: 

```xaml
<RichTextBlock html:Properties.Html="{Binding ...}"/>
```

or 

```xaml
<RichTextBlock>
    <html:Properties.Html>
        <![CDATA[
            <p>This is a list:</p>
            <ul>
                <li>Item 1</li>
                <li>Item 2</li>
                <li>Item 3</li>
            </ul>
		]]>
	</html:Properties.Html>
</RichTextBlock>
```

h1, h2 and h3 tag can apply a custom format with the following code:

```csharp
HtmlProperties.H2SpanFactory = () => new Span
{
    FontSize = 13.71,
    FontWeight = FontWeights.Light
};
```
To set a max width/height of `<img>` tags:

```csharp
HtmlProperties.ImageMaxPixelWidth = 500;
HtmlProperties.ImageMaxPixelHeight = 500;
```

All credits to https://blogs.msdn.microsoft.com/tess/2013/05/13/displaying-html-content-in-a-richtextblock/</p>