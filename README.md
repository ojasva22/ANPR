# ANPR
Automatic Number Plate Recognition Using OpenCV and Tesseract(Python)

Automatic number plate recognition (ANPR), also known as licence plate recognition (LPR), is a technology that reads vehicle registration plates. ANPR is widely used around the world by agencies such as the police force, traffic management facilities, toll agencies on pay-per-use roads, as well as parking management services.

LPR has 3 major stages.

a)License Plate Detection: This is the first and probably the most important stage of the system. It is at this stage that the position of the license plate is determined. The input at this stage is an image of the vehicle and the output is the license plate.

b)Character Segmentation: It’s at this stage the characters on the license plate are mapped out and segmented into individual images.

c)Character Recognition: This is where we wrap things up. The characters earlier segmented are identified here. We’ll be using machine learning for this.

Libraies used: OpenCV, TensorFlow, NumPy


A plate is considered present if and only if:

a) The plate falls entirely within the image bounds.

b) The plate’s width is less than 80% of the image’s width, and the plate’s height is less than 87.5% of the image’s height.

c) The plate’s width is greater than 60% of the image’s width or the plate’s height is greater than 60% of the image’s height.



