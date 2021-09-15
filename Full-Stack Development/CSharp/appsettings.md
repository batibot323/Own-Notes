# `appsettings.json`

## Store a Dictionary inside `appsettings.json` [[Blog]](https://longroadtoprogrammingmastery.wordpress.com/2021/08/26/c-put-a-dictionary-inside-the-config-appsettings-json/)

Instead of hard coding a `dictionary` like this:
```csharp
Dictionary<string, string> hardCodedDictionary = new Dictionary<string, string> {
    { "Apple", "the round fruit of a tree" },
    { "Board", "a long, thin, flat piece of wood" },
    { "Couch", "a long upholstered piece of furniture" }
```

You can store a `dictionary` inside `appsettings.json`, like this:

```csharp
{
    "DictionaryOfNouns": {
        "Apple": "the round fruit of a tree",
        "Board": "a long, thin, flat piece of wood",
        "Couch": "a long upholstered piece of furniture",
    }
}
```

Then, you can get it from the `config` with this:

```csharp
// Assume config is your access to `appsettings.json`
Dictionary<string, string> myDictionary = config.GetSection("DictionaryOfNouns")
    .Get<Dictionary<string, string>>();
};
```