safe kall:
0x336000905af158601d01573d60011458600c01573d6000803e3d6000FD5b60016000f35b
= [ 51, 96, 0, 144, 90, 241, 88, 96, 29, 1, 87, 61, 96, 1, 20, 88, 96, 12, 1, 87, 61, 96, 0, 128, 62, 61, 96, 0, 253, 91, 96, 1, 96, 0, 243, 91 ]


this is 36 bytes => equivalent in size with: push8 ? push7 ? push8 ? push7 ? MSTORE MSTORE
filled in: push8 0x12345678890abcde push7 12345678890abc push8 12345678890abcde push7 12345678890abc MSTORE MSTORE

=> push8 dec1311768467166903518 push7 dec5124095574870716 push8 dec1311768467166903518 push7 dec5124095574870716 MSTORE MSTORE
to decimals => push8 dec1311768467166903518 push7 dec5124095574870716 push8 dec1311768467166903518 push7 dec5124095574870716 MSTORE MSTORE
=> 


MSTORE MSTORE PUSH PUSH PUSH PUSH MSTORE MSTORE
(36 - 8) / 4 pushes = 7 bytes per push so:
MSTORE MSTORE PUSH7 PUSH7 PUSH7 PUSH7 MSTORE MSTORE

push7 12345678890abc = push7 dec5124095574870716

todo comment more middle  flow if correct

52526612345678890abc6612345678890abc6612345678890abc6612345678890abc5252
= 



kall wanted: 0x
336000905af158601d01573d60011458600c01573d6000803e3d6000FD5b60016000f35b
kall replacement is:
336000905af158601d01573d60011458600c01573d6000803e3d62123456526001600052

// new random anti-optimizer end bit: 
336000905af158601d01573d60011458600c01573d6000803e3d621234565260ea609c52