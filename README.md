"""
A Python implementation of binary search algorithm.
"""

from typing import Sequence, TypeVar, Optional

T = TypeVar("T")


def binary_search(sorted_collection: Sequence[T], item: T) -> Optional[int]:
    """
    Pure implementation of binary search algorithm in Python.

    :param sorted_collection: a sorted sequence of comparable elements
    :param item: element to search for
    :return: index of item in sorted_collection if found, else None

    Examples:
    >>> binary_search([0, 5, 7, 10, 15], 0)
    0
    >>> binary_search([0, 5, 7, 10, 15], 15)
    4
    >>> binary_search([0, 5, 7, 10, 15], 5)
    1
    >>> binary_search([0, 5, 7, 10, 15], 6) is None
    True
    >>> binary_search([], 1) is None
    True
    """
    left = 0
    right = len(sorted_collection) - 1

    while left <= right:
        midpoint = left + (right - left) // 2
        current_item = sorted_collection[midpoint]
        if current_item == item:
            return midpoint
        if item < current_item:
            right = midpoint - 1
        else:
            left = midpoint + 1

    return None


if __name__ == "__main__":
    import doctest

    doctest.testmod()