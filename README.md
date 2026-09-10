"""
Binary Search Algorithm in Python.

For more information, see: https://en.wikipedia.org/wiki/Binary_search_algorithm
"""

from typing import List, Optional


def binary_search(sorted_collection: List[int], item: int) -> Optional[int]:
    """
    Pure Python implementation of a binary search algorithm.

    :param sorted_collection: A sorted sequence of elements
    :param item: Element to search for
    :return: Index of the item if found, else None

    Examples:
    >>> binary_search([0, 5, 7, 10, 15], 0)
    0
    >>> binary_search([0, 5, 7, 10, 15], 15)
    4
    >>> binary_search([0, 5, 7, 10, 15], 5)
    1
    >>> binary_search([0, 5, 7, 10, 15], 6)
    >>> binary_search([], 1)
    """
    left = 0
    right = len(sorted_collection) - 1

    while left <= right:
        midpoint = (left + right) // 2
        current_item = sorted_collection[midpoint]

        if current_item == item:
            return midpoint
        elif item < current_item:
            right = midpoint - 1
        else:
            left = midpoint + 1

    return None


if __name__ == "__main__":
    import doctest

    doctest.testmod()