
Convert a file (array buffer) to byte array
```java
int[] intArray = Js.uncheckedCast(new Int8Array(file.asArrayBuffer()));
byte[] byteArray = new byte[intArray.length];
for (int j = 0; j < intArray.length; j++) byteArray[j] = (byte) intArray[j];
```

Creating a Blob
```java
String textContent = "some text content";
BlobPropertyBag blobOptions = BlobPropertyBag.create();
blobOptions.setType("text/plain");

ConstructorBlobPartsArrayUnionType data = ConstructorBlobPartsArrayUnionType.of(textContent);

Blob blob = new Blob(new ConstructorBlobPartsArrayUnionType[]{data}, blobOptions);
```

Parse JSON
```java
Object parsedObject = Global.JSON.parse(text);
```

Write JSON
```java
String json = Global.JSON.stringify(object);
```
