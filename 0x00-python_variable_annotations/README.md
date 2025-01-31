This module provides runtime support for type hints.

Consider the function below:

def surface_area_of_cube(edge_length: float) -> str:
    return f"The surface area of the cube is {6 * edge_length ** 2}."
The function surface_area_of_cube takes an argument expected to be an instance of float, as indicated by the type hint edge_length: float. The function is expected to return an instance of str, as indicated by the -> str hint.

While type hints can be simple classes like float or str, they can also be more complex. The typing module provides a vocabulary of more advanced type hints.

New features are frequently added to the typing module. The typing_extensions package provides backports of these new features to older versions of Python.

See also
“Typing cheat sheet”
A quick overview of type hints (hosted at the mypy docs)

“Type System Reference” section of the mypy docs
The Python typing system is standardised via PEPs, so this reference should broadly apply to most Python type checkers. (Some parts may still be specific to mypy.)

“Static Typing with Python”
Type-checker-agnostic documentation written by the community detailing type system features, useful typing related tools and typing best practices.

Specification for the Python Type System
The canonical, up-to-date specification of the Python type system can be found at “Specification for the Python type system”.

Type aliases
A type alias is defined using the type statement, which creates an instance of TypeAliasType. In this example, Vector and list[float] will be treated equivalently by static type checkers:

type Vector = list[float]

def scale(scalar: float, vector: Vector) -> Vector:
    return [scalar * num for num in vector]

# passes type checking; a list of floats qualifies as a Vector.
new_vector = scale(2.0, [1.0, -4.2, 5.4])
Type aliases are useful for simplifying complex type signatures. For example:

from collections.abc import Sequence

type ConnectionOptions = dict[str, str]
type Address = tuple[str, int]
type Server = tuple[Address, ConnectionOptions]

def broadcast_message(message: str, servers: Sequence[Server]) -> None:
    ...

# The static type checker will treat the previous type signature as
# being exactly equivalent to this one.
def broadcast_message(
    message: str,
    servers: Sequence[tuple[tuple[str, int], dict[str, str]]]
) -> None:
    ...
The type statement is new in Python 3.12. For backwards compatibility, type aliases can also be created through simple assignment:

Vector = list[float]
Or marked with TypeAlias to make it explicit that this is a type alias, not a normal variable assignment:

from typing import TypeAlias

Vector: TypeAlias = list[float]
