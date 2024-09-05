# sUSD
This catalog doesn't have a description

## *sUSD* Operators
## UsdAttributeAdd
<img style="width: 30%" src="images\UsdAttributeAdd.png" alt="Node UI"/>


Add UsdAttribute to UsdPrim.

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| prim | Instance | None | 
| name | String | "" | 
| type | Enum | Asset | Asset, AssetArray, Bool, BoolArray, Color3d, Color3dArray, Color3f, Color3fArray, Color3h, Color3hArray, Color4d, Color4dArray, Color4f, Color4fArray, Color4h, Color4hArray, Double, Double2, Double2Array, Double3, Double3Array, Double4, Double4Array, DoubleArray, Find, Float, Float2, Float2Array, Float3, Float3Array, Float4, Float4Array, FloatArray, Frame4d, Frame4dArray, Group, Half, Half2, Half2Array, Half3, Half3Array, Half4, Half4Array, HalfArray, Int, Int2, Int2Array, Int3, Int3Array, Int4, Int4Array, Int64, Int64Array, IntArray, Matrix2d, Matrix2dArray, Matrix3d, Matrix3dArray, Matrix4d, Matrix4dArray, Normal3d, Normal3dArray, Normal3f, Normal3fArray, Normal3h, Normal3hArray, Opaque, Point3d, Point3dArray, Point3f, Point3fArray, Point3h, Point3hArray, Quatd, QuatdArray, Quatf, QuatfArray, Quath, QuathArray, String, StringArray, TexCoord2d, TexCoord2dArray, TexCoord2f, TexCoord2fArray, TexCoord2h, TexCoord2hArray, TexCoord3d, TexCoord3dArray, TexCoord3f, TexCoord3fArray, TexCoord3h, TexCoord3hArray, TimeCode, TimeCodeArray, Token, TokenArray, UChar, UCharArray, UInt, UInt64, UInt64Array, UIntArray, Vector3d, Vector3dArray, Vector3f, Vector3fArray, Vector3h, Vector3hArray

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| attribute | Instance | None


## UsdAttributeClear
<img style="width: 30%" src="images\UsdAttributeClear.png" alt="Node UI"/>


Clears the authored value from the given UsdAttribute.
    If useTime plug is set to True, the attribute value will be cleared at the given time.
    Otherwise, the attribute value will be cleared in all time samples.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| attribute | Instance | None
| useTime | Bool | False
| time | Int | 0

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| attribute | Instance | None


## UsdAttributeConnectionAdd
<img style="width: 30%" src="images\UsdAttributeConnectionAdd.png" alt="Node UI"/>


Add connection between two UsdAttributes.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| source | Instance | None
| destination | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| destination | Instance | None


## UsdAttributeConnectionRemove
<img style="width: 30%" src="images\UsdAttributeConnectionRemove.png" alt="Node UI"/>


Remove connection between two UsdAttributes.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| source | Instance | None
| destination | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| destination | Instance | None


## UsdAttributeCopy
<img style="width: 30%" src="images\UsdAttributeCopy.png" alt="Node UI"/>


Copy Usd.Attribute from source Usd.Prim to target Usd.Prim.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| sourcePrim | Instance | None
| sourceAttribute | String | ""
| targetPrim | Instance | None
| targetAttribute | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| targetPrim | Instance | None
| targetAttribute | Instance | None


## UsdAttributeGet
<img style="width: 30%" src="images\UsdAttributeGet.png" alt="Node UI"/>


Get UsdAttribute from UsdPrim.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None
| name | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| attribute | Instance | None


## UsdAttributeRemove
<img style="width: 30%" src="images\UsdAttributeRemove.png" alt="Node UI"/>


Remove UsdAttribute .

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None
| name | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| prim | Instance | None


## UsdAttributeTypeGet
<img style="width: 30%" src="images\UsdAttributeTypeGet.png" alt="Node UI"/>


Get the type name for UsdAttribute.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| attribute | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| typeName | String | ""


## UsdAttributeValueGet
<img style="width: 30%" src="images\UsdAttributeValueGet.png" alt="Node UI"/>


Get UsdAttribute value.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| attribute | Instance | None
| useTime | Bool | False
| time | Int | 0

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| value | Instance | None


## UsdAttributeValueSet
<img style="width: 30%" src="images\UsdAttributeValueSet.png" alt="Node UI"/>


Get UsdAttribute value.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| attribute | Instance | None
| value | Instance | None
| useTime | Bool | False
| time | Int | 0

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| attribute | Instance | None


## UsdAttributesGetDict
<img style="width: 30%" src="images\UsdAttributesGetDict.png" alt="Node UI"/>


Returns a dictionary with the attribute names and their respective values.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| attributesDict | Dict | {}


## UsdInstanceNameGet
<img style="width: 30%" src="images\UsdInstanceNameGet.png" alt="Node UI"/>


Get the name of Usd instance.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| usdInstance | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| name | String | ""


## UsdInstancePathGet
<img style="width: 30%" src="images\UsdInstancePathGet.png" alt="Node UI"/>


Get the Sdf.Path for Usd instance.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| usdInstance | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| sdfPath | Instance | None
| pathString | String | ""


## UsdLayerAdd
<img style="width: 30%" src="images\UsdLayerAdd.png" alt="Node UI"/>


Adds a given source layer to the subLayerPaths of the destination layer.
    The mode plug allows to specify in which position the source layer should 
    be added in the subLayerPaths.
    By default, the mode is 'Append', meaning that the source layer will be inserted at the end of the subLayerPaths.
    Setting mode as 'Prepend', the source layer will be inserted at the beginning of the subLayerPaths.
    Setting mode as 'Insert At', the source layer will be inserted at the specified index by the position plug.

    

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| destinationLayer | Instance | None | 
| sourceLayer | Instance | None | 
| mode | Enum | Append | Append, Prepend, Insert At
| position | Int | 0 | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| sourceLayer | Instance | None


## UsdLayerCreateAnonymous
<img style="width: 30%" src="images\UsdLayerCreateAnonymous.png" alt="Node UI"/>


Creates a new anonymous layer with an optional given tag.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| tag | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| layer | Instance | None


## UsdLayerCreateNew
<img style="width: 30%" src="images\UsdLayerCreateNew.png" alt="Node UI"/>


Creates a new empty layer in the given filepath.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| filepath | FileOut | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| layer | Instance | None


## UsdLayerFindOrOpen
<img style="width: 30%" src="images\UsdLayerFindOrOpen.png" alt="Node UI"/>


Returns an existing SdfLayer with the given identifier.
    The identifier can be an absolute or relative path to an existing USD file or a URI.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| identifier | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| layer | Instance | None


## UsdLayerGet
<img style="width: 30%" src="images\UsdLayerGet.png" alt="Node UI"/>


Returns a layer in the given position from the given UsdStage layer stack.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None
| position | Int | 0
| includeSessionLayers | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| layer | Instance | None


## UsdLayerPathGet
<img style="width: 30%" src="images\UsdLayerPathGet.png" alt="Node UI"/>


Gets the path and the identifier from the given SdfLayer.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| layer | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| layerPath | String | ""
| layerIdentifier | String | ""


## UsdLoadedLayersGet
<img style="width: 30%" src="images\UsdLoadedLayersGet.png" alt="Node UI"/>


Returns all layers currently held by the layer registry.

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| loadedLayers | Instance | None


## SdfSubLayersGet
<img style="width: 30%" src="images\SdfSubLayersGet.png" alt="Node UI"/>


Get the sublayers from the given SdfLayer.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| layer | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| subLayers | Instance | None


## UsdPrimAdd
<img style="width: 30%" src="images\UsdPrimAdd.png" alt="Node UI"/>


Add UsdPrim to UsdStage.

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| stage | Instance | None | 
| primpath | String | "" | 
| primType | Enum | None | None, Backdrop, BasisCurves, BlendShape, Boundable, BoundableLightBase, Camera, Capsule, Cone, Cube, Curves, Cylinder, CylinderLight, DiskLight, DistantLight, DomeLight, Field3DAsset, FieldAsset, FieldBase, GenerativeProcedural, GeomSubset, GeometryLight, Gprim, HermiteCurves, Imageable, LightFilter, Material, Mesh, NodeGraph, NonboundableLightBase, NurbsCurves, NurbsPatch, OpenVDBAsset, PackedJointAnimation, PhysicsCollisionGroup, PhysicsDistanceJoint, PhysicsFixedJoint, PhysicsJoint, PhysicsPrismaticJoint, PhysicsRevoluteJoint, PhysicsScene, PhysicsSphericalJoint, Plane, PluginLight, PluginLightFilter, PointBased, PointInstancer, Points, PortalLight, RectLight, RenderDenoisePass, RenderPass, RenderProduct, RenderSettings, RenderSettingsBase, RenderVar, Scope, Shader, SkelAnimation, SkelRoot, Skeleton, SpatialAudio, Sphere, SphereLight, Typed, Volume, Xform, Xformable

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None
| prim | Instance | None


## UsdPrimChildAppend
<img style="width: 30%" src="images\UsdPrimChildAppend.png" alt="Node UI"/>


Append child prim to UsdPrim.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None
| child | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| prim | Instance | None
| childPrim | Instance | None


## UsdPrimCopy
<img style="width: 30%" src="images\UsdPrimCopy.png" alt="Node UI"/>


Copy UsdPrim from source UsdStage to target UsdStage.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| sourceStage | Instance | None
| sourcePrimpath | String | ""
| targetStage | Instance | None
| targetPrimpath | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| targetStage | Instance | None
| targetPrim | Instance | None


## UsdPrimDisable
<img style="width: 30%" src="images\UsdPrimDisable.png" alt="Node UI"/>


Disable UsdPrim inside UsdStage.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None
| disabled | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| prim | Instance | None


## UsdPrimDisplayColorGet
<img style="width: 30%" src="images\UsdPrimDisplayColorGet.png" alt="Node UI"/>


Get display color primvar of the given Usd prim.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| color | List | []
| indices | List | []
| interpolation | String | "constant"


## UsdPrimDisplayColorSet
<img style="width: 30%" src="images\UsdPrimDisplayColorSet.png" alt="Node UI"/>


Sets display color primvar to the given Usd prim.

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| prim | Instance | None | 
| color | List | [] | 
| indices | List | [] | 
| interpolation | Enum | constant | constant, faceVarying, uniform, varying, vertex

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| prim | Instance | None


## UsdPrimGet
<img style="width: 30%" src="images\UsdPrimGet.png" alt="Node UI"/>


Get UsdPrim from prim path inside UsdStage.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None
| primpath | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| prim | Instance | None


## UsdPrimInternalReferenceAdd
<img style="width: 30%" src="images\UsdPrimInternalReferenceAdd.png" alt="Node UI"/>


Internal reference a UsdPrim.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None
| primpath | String | ""
| reference | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| prim | Instance | None


## UsdPrimKindGet
<img style="width: 30%" src="images\UsdPrimKindGet.png" alt="Node UI"/>


Get UsdPrim Kind.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| kind | String | ""


## UsdPrimKindSet
<img style="width: 30%" src="images\UsdPrimKindSet.png" alt="Node UI"/>


Set UsdPrim Kind.

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| prim | Instance | None | 
| kind | Enum | component | assembly, component, group, model, subcomponent

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| prim | Instance | None


## UsdPrimOverride
<img style="width: 30%" src="images\UsdPrimOverride.png" alt="Node UI"/>


Add an override UsdPrim to UsdStage.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None
| primpath | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None
| prim | Instance | None


## UsdPrimPropertyNamesGet
<img style="width: 30%" src="images\UsdPrimPropertyNamesGet.png" alt="Node UI"/>


Get the list of property names of a prim.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| propertyNames | List | []


## UsdPrimPurposeGet
<img style="width: 30%" src="images\UsdPrimPurposeGet.png" alt="Node UI"/>


Get UsdPrim Purpose.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| purpose | String | ""


## UsdPrimPurposeSet
<img style="width: 30%" src="images\UsdPrimPurposeSet.png" alt="Node UI"/>


Set UsdPrim Purpose.

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| prim | Instance | None | 
| purpose | Enum | render | default, guide, proxy, render

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| prim | Instance | None


## UsdPrimReferenceAdd
<img style="width: 30%" src="images\UsdPrimReferenceAdd.png" alt="Node UI"/>


Adds a reference to a UsdPrim.
    If a valid variantSet and variantName are given, the reference will be added only
    on that specific variant. Otherwise, it will add the reference out of the variant context.

    

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| prim | Instance | None | 
| mode | Enum | Reference | Reference, Payload
| reference | Instance | None | 
| filepath | FileIn |  | 
| primpath | String | "" | 
| variantSet | Instance | None | 
| variantName | String | "" | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| prim | Instance | None


## UsdPrimReferenceGet
<img style="width: 30%" src="images\UsdPrimReferenceGet.png" alt="Node UI"/>


Get the filepaths References from a UsdPrim.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| referencesList | Instance | None
| payloadsList | Instance | None


## UsdPrimReferenceRemove
<img style="width: 30%" src="images\UsdPrimReferenceRemove.png" alt="Node UI"/>


Remove the filepath Referenced to a UsdPrim.

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| prim | Instance | None | 
| mode | Enum | Reference | Reference, Payload
| reference | Instance | None | 
| filepath | FileIn |  | 
| primpath | String | "" | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| prim | Instance | None


## UsdPrimStageGet
<img style="width: 30%" src="images\UsdPrimStageGet.png" alt="Node UI"/>


Get the UsdStage for UsdPrim.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None


## UsdPrimTypeGet
<img style="width: 30%" src="images\UsdPrimTypeGet.png" alt="Node UI"/>


Get the type name for UsdPrim.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| typeName | String | ""


## UsdSdfReferenceCreate
<img style="width: 30%" src="images\UsdSdfReferenceCreate.png" alt="Node UI"/>


Create a Usd Sdf Reference with filepath and primpath.

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| mode | Enum | Reference | Reference, Payload
| filepath | FileIn |  | 
| primpath | String | "" | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| reference | Instance | None


## UsdSdfReferenceQuery
<img style="width: 30%" src="images\UsdSdfReferenceQuery.png" alt="Node UI"/>


Get the filepath and primpath from a Usd Sdf Reference.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| reference | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| filepath | String | ""
| primpath | String | ""


## UsdShadeAttributeAdd
<img style="width: 30%" src="images\UsdShadeAttributeAdd.png" alt="Node UI"/>


Add UsdShade.Input Or UsdShade.Output to UsdShade prims.

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| prim | Instance | None | 
| name | String | "" | 
| mode | Enum | Input | Input, Output
| type | Enum | Asset | Asset, AssetArray, Bool, BoolArray, Color3d, Color3dArray, Color3f, Color3fArray, Color3h, Color3hArray, Color4d, Color4dArray, Color4f, Color4fArray, Color4h, Color4hArray, Double, Double2, Double2Array, Double3, Double3Array, Double4, Double4Array, DoubleArray, Find, Float, Float2, Float2Array, Float3, Float3Array, Float4, Float4Array, FloatArray, Frame4d, Frame4dArray, Group, Half, Half2, Half2Array, Half3, Half3Array, Half4, Half4Array, HalfArray, Int, Int2, Int2Array, Int3, Int3Array, Int4, Int4Array, Int64, Int64Array, IntArray, Matrix2d, Matrix2dArray, Matrix3d, Matrix3dArray, Matrix4d, Matrix4dArray, Normal3d, Normal3dArray, Normal3f, Normal3fArray, Normal3h, Normal3hArray, Opaque, Point3d, Point3dArray, Point3f, Point3fArray, Point3h, Point3hArray, Quatd, QuatdArray, Quatf, QuatfArray, Quath, QuathArray, String, StringArray, TexCoord2d, TexCoord2dArray, TexCoord2f, TexCoord2fArray, TexCoord2h, TexCoord2hArray, TexCoord3d, TexCoord3dArray, TexCoord3f, TexCoord3fArray, TexCoord3h, TexCoord3hArray, TimeCode, TimeCodeArray, Token, TokenArray, UChar, UCharArray, UInt, UInt64, UInt64Array, UIntArray, Vector3d, Vector3dArray, Vector3f, Vector3fArray, Vector3h, Vector3hArray

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| prim | Instance | None
| shadeAttribute | Instance | None


## UsdShadeAttributeGet
<img style="width: 30%" src="images\UsdShadeAttributeGet.png" alt="Node UI"/>


Get UsdShade.Input Or UsdShade.Output belong to UsdShade prims.

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| prim | Instance | None | 
| name | String | "" | 
| mode | Enum | Input | Input, Output

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| shadeAttribute | Instance | None


## UsdStage
<img style="width: 30%" src="images\UsdStage.png" alt="Node UI"/>


Defines an USD stage instance.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None


## UsdStageDefaultPrimClear
<img style="width: 30%" src="images\UsdStageDefaultPrimClear.png" alt="Node UI"/>


Clears the default prim layer metadata in the given UsdStage root layer.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None


## UsdStageDefaultPrimGet
<img style="width: 30%" src="images\UsdStageDefaultPrimGet.png" alt="Node UI"/>


Gets the default prim in the given UsdStage root layer.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| prim | Instance | None


## UsdStageDefaultPrimSet
<img style="width: 30%" src="images\UsdStageDefaultPrimSet.png" alt="Node UI"/>


Sets the default prim to the given UsdStage root layer.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None
| prim | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None


## UsdStageEditTargetGet
<img style="width: 30%" src="images\UsdStageEditTargetGet.png" alt="Node UI"/>


Returns the current edit target and its associated layer from the given USD stage.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| editTarget | Instance | None
| editTargetLayer | Instance | None


## UsdStageEditTargetSet
<img style="width: 30%" src="images\UsdStageEditTargetSet.png" alt="Node UI"/>


Sets the edit target to the given USD stage using the given layer.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None
| layer | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None
| layer | Instance | None


## UsdStageFlatten
<img style="width: 30%" src="images\UsdStageFlatten.png" alt="Node UI"/>


Returns a single, anonymous, merged SdfLayer from the given UsdStage or SdfLayer, and a UsdStage that uses the resulting merged layer.
    If a UsdStage is passed, the operator do the merge from the root layer of the UsdStage.
    Otherwise, if a SdfLayer is passed, the operator needs to use a temporary UsdStage to compute the flattening using the given layer.
    If both inputs are given, the SdfLayer has priority over the UsdStage.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None
| layer | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None
| flattenLayer | Instance | None


## UsdStageMetadataGet
<img style="width: 30%" src="images\UsdStageMetadataGet.png" alt="Node UI"/>


Get UsdStage metadata.

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| stage | Instance | None | 
| metadataKey | Enum | comment | comment, defaultPrim, documentation, endFrame, endTimeCode, metersPerUnit, renderSettingsPrimPath, startFrame, startTimeCode, timeCodesPerSecond, upAxis

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None
| metadataValue | Object | None


## UsdStageMetadataSet
<img style="width: 30%" src="images\UsdStageMetadataSet.png" alt="Node UI"/>


Set UsdStage metadata.

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| stage | Instance | None | 
| metadataKey | Enum | comment | comment, defaultPrim, documentation, endFrame, endTimeCode, metersPerUnit, renderSettingsPrimPath, startFrame, startTimeCode, timeCodesPerSecond, upAxis
| metadataValue | Object | None | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None


## UsdStageNew
<img style="width: 30%" src="images\UsdStageNew.png" alt="Node UI"/>


Creating a new USD stage instance. The filepath (or identifier) should be written in a valid USD file format.
    If no filepath is provided, the stage will be created in memory as an anonymous layer.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| filepath | FileOut | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None


## UsdStageOpen
<img style="width: 30%" src="images\UsdStageOpen.png" alt="Node UI"/>


Open a new USD stage instance from the given file path.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| filepath | FileIn | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None


## UsdStageRootLayerGet
<img style="width: 30%" src="images\UsdStageRootLayerGet.png" alt="Node UI"/>


Returns the root layer from the given UsdStage.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None
| rootLayer | Instance | None


## UsdStageSave
<img style="width: 30%" src="images\UsdStageSave.png" alt="Node UI"/>


Save an exist USD stage instance .

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None
| filepath | FileOut | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| filepath | String | ""


## UsdStageSessionLayerGet
<img style="width: 30%" src="images\UsdStageSessionLayerGet.png" alt="Node UI"/>


Returns the session layer from the given UsdStage.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None
| sessionLayer | Instance | None


## UsdStageToString
<img style="width: 30%" src="images\UsdStageToString.png" alt="Node UI"/>


Converts the stage dada into a flattened Usd text representation.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| result | Code | None


## UsdStageSubLayerAdd
<img style="width: 30%" src="images\UsdStageSubLayerAdd.png" alt="Node UI"/>


Add UsdLayer to the UsdStage subLayerPaths using the given file path.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None
| filepath | FileIn | 
| index | Int | -1

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None


## UsdStageLayerStackGet
<img style="width: 30%" src="images\UsdStageLayerStackGet.png" alt="Node UI"/>


Get the layer stack from the given UsdStage.
    If includeSessionLayers is set to True, the result list will include the session layer.
    Otherwise, the session layer will be skipped from the result list.
    If includeMutedLayers is set to True, the muted layers will be included in the result list in the same order of the stack.
    Otherwise, the muted layers will be skipped from the result list.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None
| includeSessionLayers | Bool | False
| includeMutedLayers | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| layers | Instance | None


## UsdStageSubLayerRemove
<img style="width: 30%" src="images\UsdStageSubLayerRemove.png" alt="Node UI"/>


Remove UsdLayer to the UsdStage subLayerPaths using the given file path.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None
| filepath | FileIn | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None


## UsdStageTraverse
<img style="width: 30%" src="images\UsdStageTraverse.png" alt="Node UI"/>


Traverses the UsdStage and returns the UsdPrims that are active, defined, loaded, and concrete.
    If primtype is not 'Any', it will filter by the selected prim type. Otherwise, it will return all the prims without filtering.
    If traverseAll is checked, it will return also the inactive prims. Otherwise, only the active ones.

    

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| stage | Instance | None | 
| primType | Enum | Any | Any, Backdrop, BasisCurves, BlendShape, Boundable, BoundableLightBase, Camera, Capsule, Cone, Cube, Curves, Cylinder, CylinderLight, DiskLight, DistantLight, DomeLight, Field3DAsset, FieldAsset, FieldBase, GenerativeProcedural, GeomSubset, GeometryLight, Gprim, HermiteCurves, Imageable, LightFilter, Material, Mesh, NodeGraph, NonboundableLightBase, NurbsCurves, NurbsPatch, OpenVDBAsset, PackedJointAnimation, PhysicsCollisionGroup, PhysicsDistanceJoint, PhysicsFixedJoint, PhysicsJoint, PhysicsPrismaticJoint, PhysicsRevoluteJoint, PhysicsScene, PhysicsSphericalJoint, Plane, PluginLight, PluginLightFilter, PointBased, PointInstancer, Points, PortalLight, RectLight, RenderDenoisePass, RenderPass, RenderProduct, RenderSettings, RenderSettingsBase, RenderVar, Scope, Shader, SkelAnimation, SkelRoot, Skeleton, SpatialAudio, Sphere, SphereLight, Typed, Volume, Xform, Xformable
| traverseAll | Bool | False | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| prims | Instance | None


## UsdStageUpAxisGet
<img style="width: 30%" src="images\UsdStageUpAxisGet.png" alt="Node UI"/>


Get the UsdStage's up axis.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| stage | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| upAxis | String | ""


## UsdStageUpAxisSet
<img style="width: 30%" src="images\UsdStageUpAxisSet.png" alt="Node UI"/>


Set the UsdStage's up axis, which must be Y or Z.

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| stage | Instance | None | 
| upAxis | Enum | Y | Y, Z

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| stage | Instance | None


## UsdSubLayersPathGet
<img style="width: 30%" src="images\UsdSubLayersPathGet.png" alt="Node UI"/>


Get the sublayers paths from the given SdfLayer.
    If includeParentLayer is set to True, the given parent layer will be added
    at the beginning of the result list. Otherwise, the parent layer won't be included.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| parentLayer | Instance | None
| includeParentLayer | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| layersPaths | List | []


## UsdVariantAdd
<img style="width: 30%" src="images\UsdVariantAdd.png" alt="Node UI"/>


Adds a variant with the given name to the input variant set.


    @param code str: code name of the operator.
    @param parent shift.core.workflow.SWorkflow: the workflow owning the operator.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| variantSet | Instance | None
| variantName | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| variantSet | Instance | None


## UsdVariantGetAll
<img style="width: 30%" src="images\UsdVariantGetAll.png" alt="Node UI"/>


Get all variants for the input variant set.


    @param code str: code name of the operator.
    @param parent shift.core.workflow.SWorkflow: the workflow owning the operator.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| variantSet | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| variantsList | List | []


## UsdVariantGetSelected
<img style="width: 30%" src="images\UsdVariantGetSelected.png" alt="Node UI"/>


Get the selected variant for the input variant set.


    @param code str: code name of the operator.
    @param parent shift.core.workflow.SWorkflow: the workflow owning the operator.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| variantSet | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| variantName | String | ""


## UsdVariantSetAdd
<img style="width: 30%" src="images\UsdVariantSetAdd.png" alt="Node UI"/>


Adds a variant set to the prim.


    @param code str: code name of the operator.
    @param parent shift.core.workflow.SWorkflow: the workflow owning the operator.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None
| variantSetName | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| variantSet | Instance | None


## UsdVariantSetGet
<img style="width: 30%" src="images\UsdVariantSetGet.png" alt="Node UI"/>


Get a variant set to the prim.


    @param code str: code name of the operator.
    @param parent shift.core.workflow.SWorkflow: the workflow owning the operator.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None
| variantSetName | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| variantSet | Instance | None


## UsdVariantSetSelected
<img style="width: 30%" src="images\UsdVariantSetSelected.png" alt="Node UI"/>


Set the selected variant for the input variant set.


    @param code str: code name of the operator.
    @param parent shift.core.workflow.SWorkflow: the workflow owning the operator.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| variantSet | Instance | None
| variantName | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| variantSet | Instance | None


## UsdVariantWorkflow
<img style="width: 30%" src="images\UsdVariantWorkflow.png" alt="Node UI"/>


The variant workflow operator executes an external Shift workflow within a USD variant context.
    The operator expands its plugs dynamically to enable access to its input and output data.


    @param code str: code name of the operator.
    @param parent shift.core.workflow.SWorkflow: the workflow owning the operator.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| file | FileIn | 
| variantSet | Instance | None
| variant | String | ""

## UsdXformSet
<img style="width: 30%" src="images\UsdXformSet.png" alt="Node UI"/>


Set UsdGeom xform operations.

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| prim | Instance | None
| usetime | Bool | False
| time | Float | 0.0
| translate | Object | None
| rotate | Object | None
| scale | Object | None
| pivot | Object | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| prim | Instance | None


