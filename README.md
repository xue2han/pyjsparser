# pyjsparser
[![Build Status](https://travis-ci.org/PiotrDabkowski/pyjsparser.svg?branch=master)](https://travis-ci.org/PiotrDabkowski/pyjsparser)

Fast JavaScript parser - manual translation of esprima.js to python. Takes 1 second to parse whole angular.js library so parsing speed is about 100k characters per second which makes it the fastest and most comprehensible JavaScript parser for python out there.

Supports whole ECMAScript 5.1 and parts of ECMAScript 6. 

# Installation 

    pip install pyjsparser
    
# Example
    
    >>> from pyjsparser import PyJsParser
    >>> p = PyJsParser()
    >>> p.parse('var $ = "Hello!"')
    {
    "type": "Program",
    "body": [
        {
            "type": "VariableDeclaration",
            "declarations": [
                {
                    "type": "VariableDeclarator",
                    "id": {
                        "type": "Identifier",
                        "name": "$"
                    },
                    "init": {
                        "type": "Literal",
                        "value": "Hello!",
                        "raw": '"Hello!"'
                    }
                }
            ],
            "kind": "var"
        }
      ]
    }
