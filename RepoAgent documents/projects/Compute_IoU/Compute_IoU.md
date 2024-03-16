## FunctionDef Cal_IoU(GT_bbox, Pred_bbox)
**Cal_IoU**: The function of Cal_IoU is to calculate the Intersection over Union (IoU) between two bounding boxes.

**parameters**:
- GT_bbox: the bounding box of the ground truth.
- Pred_bbox: the bounding box of the predicted.

**Code Description**:
The function first calculates the intersecting area between the two bounding boxes by finding the maximum values for the top-left corner and the minimum values for the bottom-right corner. It then computes the area of the intersection and the total area covered by both bounding boxes. Finally, it calculates the IoU by dividing the intersection area by the total area.

**Note**:
- Make sure the bounding box coordinates are in the format [x_min, y_min, x_max, y_max].
- The IoU value ranges from 0 to 1, where 0 indicates no overlap and 1 indicates complete overlap.

**Output Example**:
0.75
