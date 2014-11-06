Change fbx import scale
=======================

```csharp

using UnityEditor;
 
public class FBXScaleFix : AssetPostprocessor
{
    public void OnPreprocessModel()
    {
        ModelImporter modelImporter = (ModelImporter) assetImporter;                    
        modelImporter.globalScale = 1;          
    }   
}

```