# Assignment #2: Supermarket

## Problem

You are tasked with developing a system to manage the inventory of produced goods(egg, milk, bread, etc.) for a supermarket.  
The system should ensure that the freshest products (the most recently produced ones) are sold first, while products that have expired should not be sold.

Each product in the inventory has the following properties:

- `id`: An integer representing the unique identifier for the product.

- `current_timestamp`: An integer representing the Unix timestamp at the time the method is called. This value is used to determine the current time and is guaranteed to be monotonically increasing.

- `expires_in`: An integer representing the duration in seconds until the product expires (from the `current_timestamp`). The product is immediately unavailable for sale once it reaches its expiration.

Implement the `ProductInventory` class:

- `add_product(current_timestamp, id, expires_in)`: Adds a product with the specified `id` to the inventory. The product expires in `expires_in` seconds from the `current_timestamp`.

- `sell_product(current_timestamp)`: Removes the *most recently added product* that has not expired from the inventory and returns its `id`. If no product is available for sale, return `-1`.

- `get_inventory(current_timestamp)`: Returns a list of all product `id`s currently in the inventory that have not expired, sorted by the timestamp they were added to the inventory, from the freshest to the oldest.

슈퍼마켓에서 상품(계란, 우유, 빵 등)의 재고를 관리하는 시스템을 개발하세요. 이 시스템은 **가장 최근에 생산된 제품**이 우선적으로 판매되도록 해야 하며, 유통기한이 지난 제품은 판매되면 안됩니다.

재고에 있는 각 제품은 다음과 같은 속성을 가집니다:

- `id`: 제품의 고유 식별자를 나타내는 정수.

- `current_timestamp`: 메서드가 호출된 시점의 Unix 타임스탬프를 나타내는 정수. 이 값은 현재 시간을 나타내며, **단조 증가(monotonically increasing)**가 보장됩니다.

- `expires_in`: 제품이 유통기한에 도달하기까지 남은 시간을 나타내는 정수 (초 단위, `current_timestamp` 기준). 유통기한이 도달하는 즉시 상품은 판매할 수 없습니다.

`ProductInventory` 클래스를 구현하세요:

- `add_product(current_timestamp, id, expires_in)`: 주어진 `id`를 가진 제품을 재고에 추가합니다. 해당 제품의 유통기한은 `current_timestamp`기준으로 `expires_in`초 후까지입니다.  

- `sell_product(current_timestamp)`: 유통기한이 지나지 않은 *가장 최근에 추가된 제품*을 재고에서 제거하고 해당 제품의 `id`를 반환합니다. 판매할 수 있는 제품이 없으면 `-1`을 반환합니다.  

- `get_inventory(current_timestamp)`: 호출된 `current_timestamp` 시점을 기준으로 재고에 있는 유통기한이 지나지 않은 모든 제품의 `id` 목록을 반환합니다. 목록은 *재고에 추가된 시점*의 타임스탬프를 기준으로 가장 신선한 제품부터 오래된 제품 순서로 정렬되어야 합니다.

## Input specification

The names of the functions and their respective parameters will be provided in the order they are called.

Functions will be separated by a newline, and the parameters of the functions will be separated by whitespace.

함수의 이름과 해당 매개변수들이 호출된 순서대로 제공됩니다.

각 함수 호출은 개행(newline)으로 구분되며, 함수의 매개변수들은 공백으로 구분됩니다.

## Output specification

For each call to `sell_product(current_timestamp)`, output the `id` of the product that is sold, or -1 if no product is sold, followed by a single newline.

For each call to `get_inventory()`, output the list of product `id`s in the inventory, separated by a comma and a whitespace, surrounded by brackets `[]`, followed by a single newline. e.g., `[1, 2, 3]`.

`sell_product(current_timestamp)`가 호출될 때마다, 판매된 제품의 `id`를 출력하고, 판매할 제품이 없다면 `-1`을 출력합니다. 출력 후 개행(newline)을 추가합니다.  

`get_inventory()`가 호출될 때마다, 현재 재고에 있는 제품들의 `id` 목록을 출력합니다. 출력 형식은 쉼표(`,`)로 구분된 `id` 목록을 대괄호(`[]`)로 감싸야 합니다. 출력 후 개행(newline)을 추가합니다. 예시: `[1, 2, 3]`

### Sample 0

```plaintext
<< in
add_product 1001 1 100
add_product 1002 2 200
add_product 1003 3 300
sell_product 1200
sell_product 1300
add_product 1404 4 400
get_inventory 1500
add_product 1505 5 500
get_inventory 1600

>> out
3
-1
[4]
[5, 4]
```

### Sample  1

```plaintext
<< in
get_inventory 1000
add_product 1001 1 100
sell_product 1101
add_product 1102 2 200
add_product 1103 3 300
get_inventory 1200
sell_product 1201
sell_product 1202
add_product 1204 4 400
add_product 1205 5 500
get_inventory 1300
sell_product 1301
get_inventory 2000
add_product 2001 6 600

>> out
[]
-1
[3, 2]
3
2
[5, 4]
5
[]
```
