# Operation Set `opset2` Specification

This specification document describes `opset2` operation set supported in OpenVINO.
Support for each particular operation from the list below depends on the capabilities available in a inference plugin
and may vary among different hardware platforms and devices. Examples of operation instances are expressed as IR V10 xml
snippets. Such IR is generated by the Model Optimizer. The semantics match corresponding nGraph operation classes
declared in `namespace opset2`.


## Table of Contents <a name="toc"></a>

* [Abs](./docs/ops/arithmetic/Abs_1.md)
* [Acos](./docs/ops/arithmetic/Acos_1.md)
* [Add](./docs/ops/arithmetic/Add_1.md)
* [Asin](./docs/ops/arithmetic/Asin_1.md)
* [Atan](./docs/ops/arithmetic/Atan_1.md)
* [AvgPool](./docs/ops/pooling/AvgPool_1.md)
* [BatchNormInference](./docs/ops/normalization/BatchNormInference_1.md)
* [BatchToSpace](./docs/ops/movement/BatchToSpace_2.md)
* [BinaryConvolution](./docs/ops/convolution/BinaryConvolution_1.md)
* [Broadcast](./docs/ops/movement/Broadcast_1.md)
* [CTCGreedyDecoder](./docs/ops/sequence/CTCGreedyDecoder_1.md)
* [Ceiling](./docs/ops/arithmetic/Ceiling_1.md)
* [Clamp](./docs/ops/activation/Clamp_1.md)
* [Concat](./docs/ops/movement/Concat_1.md)
* [Constant](./docs/ops/infrastructure/Constant_1.md)
* [Convert](./docs/ops/type/Convert_1.md)
* [ConvertLike](./docs/ops/type/ConvertLike_1.md)
* [Convolution](./docs/ops/convolution/Convolution_1.md)
* [ConvolutionBackpropData](./docs/ops/convolution/ConvolutionBackpropData_1.md)
* [Cos](./docs/ops/arithmetic/Cos_1.md)
* [Cosh](./docs/ops/arithmetic/Cosh_1.md)
* [DeformableConvolution](./docs/ops/convolution/DeformableConvolution_1.md)
* [DeformablePSROIPooling](./docs/ops/detection/DeformablePSROIPooling_1.md)
* [DepthToSpace](./docs/ops/movement/DepthToSpace_1.md)
* [DetectionOutput](./docs/ops/detection/DetectionOutput_1.md)
* [Divide](./docs/ops/arithmetic/Divide_1.md)
* [Elu](./docs/ops/activation/Elu_1.md)
* [Equal](./docs/ops/comparison/Equal_1.md)
* [Erf](./docs/ops/arithmetic/Erf_1.md)
* [Exp](./docs/ops/activation/Exp_1.md)
* [FakeQuantize](./docs/ops/quantization/FakeQuantize_1.md)
* [Floor](./docs/ops/arithmetic/Floor_1.md)
* [FloorMod](./docs/ops/arithmetic/FloorMod_1.md)
* [Gather](./docs/ops/movement/Gather_1.md)
* [GatherTree](./docs/ops/movement/GatherTree_1.md)
* [Gelu](./docs/ops/activation/GELU_2.md)
* [Greater](./docs/ops/comparison/Greater_1.md)
* [GreaterEqual](./docs/ops/comparison/GreaterEqual_1.md)
* [GRN](./docs/ops/normalization/GRN_1.md)
* [GroupConvolution](./docs/ops/convolution/GroupConvolution_1.md)
* [GroupConvolutionBackpropData](./docs/ops/convolution/GroupConvolutionBackpropData_1.md)
* [HardSigmoid](./docs/ops/activation/HardSigmoid_1.md)
* [Interpolate](./docs/ops/image/Interpolate_1.md)
* [Less](./docs/ops/comparison/Less_1.md)
* [LessEqual](./docs/ops/comparison/LessEqual_1.md)
* [Log](./docs/ops/arithmetic/Log_1.md)
* [LogicalAnd](./docs/ops/logical/LogicalAnd_1.md)
* [LogicalNot](./docs/ops/logical/LogicalNot_1.md)
* [LogicalOr](./docs/ops/logical/LogicalOr_1.md)
* [LogicalXor](./docs/ops/logical/LogicalXor_1.md)
* [LRN](./docs/ops/normalization/LRN_1.md)
* [LSTMCell](./docs/ops/sequence/LSTMCell_1.md)
* [LSTMSequence](./docs/ops/sequence/LSTMSequence_1.md)
* [MatMul](./docs/ops/matrix/MatMul_1.md)
* [MaxPool](./docs/ops/pooling/MaxPool_1.md)
* [Maximum](./docs/ops/arithmetic/Maximum_1.md)
* [Minimum](./docs/ops/arithmetic/Minimum_1.md)
* [Mod](./docs/ops/arithmetic/Mod_1.md)
* [MVN](./docs/ops/normalization/MVN_1.md)
* [Multiply](./docs/ops/arithmetic/Multiply_1.md)
* [Negative](./docs/ops/arithmetic/Negative_1.md)
* [NonMaxSuppression](./docs/ops/sort/NonMaxSuppression_1.md)
* [NormalizeL2](./docs/ops/normalization/NormalizeL2_1.md)
* [NotEqual](./docs/ops/comparison/NotEqual_1.md)
* [OneHot](./docs/ops/sequence/OneHot_1.md)
* [Pad](./docs/ops/movement/Pad_1.md)
* [Parameter](./docs/ops/infrastructure/Parameter_1.md)
* [Power](./docs/ops/arithmetic/Power_1.md)
* [PReLU](./docs/ops/activation/PReLU_1.md)
* [PriorBoxClustered](./docs/ops/detection/PriorBoxClustered_1.md)
* [PriorBox](./docs/ops/detection/PriorBox_1.md)
* [Proposal](./docs/ops/detection/Proposal_1.md)
* [PSROIPooling](./docs/ops/detection/PSROIPooling_1.md)
* [Range](./docs/ops/generation/Range_1.md)
* [ReLU](./docs/ops/activation/ReLU_1.md)
* [ReduceLogicalAnd](./docs/ops/reduction/ReduceLogicalAnd_1.md)
* [ReduceLogicalOr](./docs/ops/reduction/ReduceLogicalOr_1.md)
* [ReduceMax](./docs/ops/reduction/ReduceMax_1.md)
* [ReduceMean](./docs/ops/reduction/ReduceMean_1.md)
* [ReduceMin](./docs/ops/reduction/ReduceMin_1.md)
* [ReduceProd](./docs/ops/reduction/ReduceProd_1.md)
* [ReduceSum](./docs/ops/reduction/ReduceSum_1.md)
* [RegionYolo](./docs/ops/detection/RegionYolo_1.md)
* [ReorgYolo](./docs/ops/detection/ReorgYolo_1.md)
* [Reshape](./docs/ops/shape/Reshape_1.md)
* [Result](./docs/ops/infrastructure/Result_1.md)
* [ReverseSequence](./docs/ops/movement/ReverseSequence_1.md)
* [ROIPooling](./docs/ops/detection/ROIPooling_1.md)
* [Select](./docs/ops/condition/Select_1.md)
* [Selu](./docs/ops/arithmetic/Selu_1.md)
* [ShapeOf](./docs/ops/shape/ShapeOf_1.md)
* [Sigmoid](./docs/ops/activation/Sigmoid_1.md)
* [Sign](./docs/ops/arithmetic/Sign_1.md)
* [Sin](./docs/ops/arithmetic/Sin_1.md)
* [Sinh](./docs/ops/arithmetic/Sinh_1.md)
* [SoftMax](./docs/ops/activation/SoftMax_1.md)
* [SpaceToBatch](./docs/ops/movement/SpaceToBatch_2.md)
* [SpaceToDepth](./docs/ops/movement/SpaceToDepth_1.md)
* [Split](./docs/ops/movement/Split_1.md)
* [Sqrt](./docs/ops/arithmetic/Sqrt_1.md)
* [SquaredDifference](./docs/ops/arithmetic/SquaredDifference_1.md)
* [Squeeze](./docs/ops/shape/Squeeze_1.md)
* [StridedSlice](./docs/ops/movement/StridedSlice_1.md)
* [Subtract](./docs/ops/arithmetic/Subtract_1.md)
* [Tan](./docs/ops/arithmetic/Tan_1.md)
* [Tanh](./docs/ops/arithmetic/Tanh_1.md)
* [TensorIterator](./docs/ops/infrastructure/TensorIterator_1.md)
* [Tile](./docs/ops/movement/Tile_1.md)
* [TopK](./docs/ops/sort/TopK_1.md)
* [Transpose](./docs/ops/movement/Transpose_1.md)
* [Unsqueeze](./docs/ops/shape/Unsqueeze_1.md)
* [VariadicSplit](./docs/ops/movement/VariadicSplit_1.md)
