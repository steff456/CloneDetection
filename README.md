# CloneDetection
Detect clones in a cross-language setting

To generate the Parser, Lexer and Visitor classes please use ANTLR4,
```
conda create -n test python=3.8
pip install antlr4-python3-runtime
```

Download any grammar defined in ANTLR4 and run the following command,
```
java -cp antlr-4.7.1-complete.jar org.antlr.v4.Tool -Dlanguage=Python3 -visitor ../clone_detection/grammars/XXX
```

```
python -m clone_detection --f examples/sort/bubble_sort.kt examples/sort/bubble_sort.dart
```

# Universal nodes definition

| Node   Name    | Description                                |
|--------------------------|------------------------------------------------------|
| File                     | File node                                            |
| Script                   | Script node                                          |
| Identifier               | Actual name for functions, classes and variables     |
| Class_decl              | Class declaration                                    |
| Constructor_decl        | Constructor declaration                              |
| Parameter_list          | List of parameters                                   |
| Parameter                | Single parameter node                                |
| Constructor_call        | Create new object from constructor                   |
| Class_body              | Body of a class                                      |
| Class_member            | Member of a class                                    |
| Enum_decl               | Enumeration declaration                              |
| Enum_body               | Body of an enumeration                               |
| Function_decl           | Function declaration                                 |
| Function_body           | Body of function                                     |
| Function_call           | Function call                                        |
| Attribute_decl          | Attribute declaration                                |
| Variable_decl           | Variable declaration                                 |
| Getter                   | Getter declaration                                   |
| Setter                   | Setter declaration                                   |
| Type_alias              | Define a shorter name type that the user can create  |
| Parameter_type          | Type of parameter                                    |
| Type                     | Data type                                            |
| Nullable_type           | Nullable type                                        |
| Function_type           | Function type                                        |
| User_type               | Custom user type                                     |
| Or                       | Define two conjuctions separated by an or statement  |
| And                      | Define two conjuctions separated by an and statement |
| Ternary                  | Ternary or elvis operation                           |
| As                       | As expression used for casting                       |
| Prefix                   | Define a prefix operation ++, --, +=, -=, etc        |
| Posfix                   | Define a posfix operation ++, --, +=, -=, etc        |
| Collection_indexing     | Index a collection                                   |
| Value_argument_list    | List of arguments used in a call                     |
| Value_argument          | Value of a single argument                           |
| Type_argument_list     | List of type arguments                               |
| Type_argument           | Value of a single argument                           |
| String                   | String literal                                       |
| Collection               | Define a collection                                  |
| Super_call              | Call to super function                               |
| Condition                | Condition declaration                                |
| Body                     | Body of a control structure                          |
| Try                      | Try block structure                                  |
| Catch                    | Catch block structure                                |
| Finally                  | Finally block structure                              |
| Loop_statement          | Loop statement definition                            |
| Jump_statement          | Jump statement definition                            |
| Equality_operator       | Equality operation                                   |
| Comparison_operator     | Comparison operation                                 |
| Member_of               | Determine if x is in a container                     |
| Is_type                 | Determine the type of x                              |
| Additive_operator       | Additive or substraction operation                   |
| Multiplicative_operator | Multiplication/division/modulus operation            |
| Logical_operator        | Logical operation                                    |
| Access_operator         | Acess operator                                       |
| Visibility_modifier     | Define if the visibility of a member of a class      |
| Const_decl              | Constant declaration                                 |
| Inheritance_modifier    | Declare if the inheritance is abstract or final      |
| Literal                  | Defines the user's value or naming                   |
| Assignment_operator     | Assignment operation                                 |
| Expression               | Group expressions of the language                    |
| Throw                    | Throw exception expression                           |
| This                     | Define a reference to the instance of the class      |
| Await_expression        | Await expression                                     |
| Assert                   | Assert expression                                    |



# Similar universal nodes mapping

| Node   Name     | Similar node names                                       |
|--------------------------|-------------------------------------------------------------------|
| Identifier               | Literal, Identifier                                               |
| Class_decl              | Class_decl                                                       |
| Constructor_decl        | Constructor_decl                                                 |
| Parameter_list          | Parameter_list, Value_argument_list                            |
| Parameter                | Parameter                                                         |
| Constructor_call        | Constructor_call                                                 |
| Class_body              | Class_body                                                       |
| Class_member            | Class_member                                                     |
| Enum_decl               | Enum_decl                                                        |
| Enum_body               | Enum_body                                                        |
| Function_decl           | Function_decl                                                    |
| Function_body           | Function_body                                                    |
| Function_call           | Function_call                                                    |
| Attribute_decl          | Attribute_decl, Variable_decl                                   |
| Variable_decl           | Variable_decl, Attribute_decl                                   |
| Getter                   | Getter                                                            |
| Setter                   | Setter                                                            |
| Type_alias              | Type_alias                                                       |
| Parameter_type          | Parameter_type, Type                                             |
| Type                     | Type, Parameter_type, Nullable_type, Function_type, User_type |
| Nullable_type           | Nullable_type, Type                                              |
| Function_type           | Function_type, Type                                              |
| User_type               | User_type, Type                                                  |
| Or                       | Or                                                                |
| And                      | And                                                               |
| Ternary                  | Ternary                                                           |
| As                       | As                                                                |
| Prefix                   | Prefix                                                            |
| Posfix                   | Posfix                                                            |
| Collection_indexing     | Collection_indexing                                              |
| Value_argument_list    | Parameter_list, Value_argument_list                            |
| Value_argument          | Value_argument                                                   |
| Type_argument_list     | Type_argument_list                                              |
| Type_argument           | Type_argument                                                    |
| String                   | String                                                            |
| Collection               | Collection                                                        |
| Super_call              | Super_call                                                       |
| Condition                | Condition                                                         |
| Body                     | Body                                                              |
| Try                      | Try                                                               |
| Catch                    | Catch                                                             |
| Finally                  | Finally                                                           |
| Loop_statement          | Loop_statement                                                   |
| Jump_statement          | Jump_statement                                                   |
| Equality_operator       | Equality_operator                                                |
| Comparison_operator     | Comparison_operator                                              |
| Member_of               | Member_of                                                        |
| Is_type                 | Is_type                                                          |
| Additive_operator       | Additive_operator                                                |
| Multiplicative_operator | Multiplicative_operator                                          |
| Logical_operator        | Logical_operator                                                 |
| Access_operator         | Access_operator                                                  |
| Visibility_modifier     | Visibility_modifier                                              |
| Const_decl              | Const_decl                                                       |
| Inheritance_modifier    | Inheritance_modifier                                             |
| Literal                  | Literal                                                           |
| Assignment_operator     | Assignment_operator                                              |
| Expression               | Expression                                                        |
| Throw                    | Throw                                                             |
| This                     | This                                                              |
| Await_expression        | Await_expression                                                 |
| Assert                   | Assert                                                            |

