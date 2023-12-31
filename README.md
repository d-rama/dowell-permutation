
# DoWell-Permutation Python Library

Welcome to the Permutation API! The Permutation API is a comprehensive tool that enables users to generate permutations of a set of items efficiently. It provides a reliable and high-performance solution for permutation calculations, making it ideal for a wide range of applications such as combinatorial optimization, data analysis, and algorithm design.

## Installation
1.  Installing the library
    ```sh 
    pip install dowell-permutation
    ```
2. Create an instance of the API
    ```python
    from permutation import Permutation
    perm = Pemutation()
    ```

## Features

The Permutation API offers the following key features:

- ```Total Number of Permutations Possible``` : this feature calculates the precise count of all the potential permutations based on the provided values of ```'n'``` and ```'r'```. 
- ```Exact Permutations``` : this feature allows users to find the precise permutations for any given range of ```'n'``` and ```'r'```. This feature utilizes a specially designed algorithm that ensures accurate and efficient permutation generation.

```Note``` : ```'n'``` is total number of items present and ```'r'``` is the total number of items to be selected from ```'r'```.

The library offers three main methods through the instance

1. Find permuation
    ```python
    perm.find(n, r, next_variable)
    
    """
        Generates permutations based on the given parameters. It sends a JSON payload using the provided params
        :param n: The total number of elements available for permutation
        :param r: The number of elements to be selected in each permutation
        :param next_variable: The next variable to be included in the permutation
        :return: response returns the generated permutation in JSON format. The response body contains the following information:
        eventId: An event ID associated with the permutation.
        n: The total number of elements available for permutation.
        r: The number of elements selected in each permutation.
        numberOfPermutations: The total number of possible permutations.
        permutationVariables: An array of arrays, where each inner array represents a permutation with the selected variables.
        inserted_id: The ID of the inserted permutation.
    """
    ```
2. Save Permutation
    ```python
    perm.save(inserted_id, selected_permutations)
    
    """
        Saves a selected permutation. It sends a JSON payload with the parameters provided
        :param id: The ID of the permutation to be saved
        :param selected_permutation: An array of variables representing the selected permutation
        :return: The response confirms the successful saving of the permutation. The response body contains a success message.
    """
    
    ```
3. Show Permutaion
    ```python
    perm.retrieve(id)
    
    """
        Retrieves a specific permutation based on its ID
        :param id:
        :return: the requested permutation in JSON format. The response body contains the following information:
        eventId: An event ID associated with the permutation.
        n: The total number of elements available for permutation.
        r: The number of elements selected in each permutation.
        permutationVariables: An array representing the selected permutation.
        inserted_id: The ID of the permutation.
    """
    ```

## More about the API

To get started with the Permutation API, follow these steps:

1. Review the [API Documentation](https://documenter.getpostman.com/view/27523601/2s93mAVL3e) to understand the available endpoints, request parameters, and response formats.

2. Make API requests to calculate the total number of permutations possible and to find the exact permutations by providing the ```'n'``` , ```'r'``` , and the exact values for each item.

3. Analyze the returned results, including the number of permutations and the final permutation.

## Example

Here is an example of how you can use the Permutation Library:

1. Imagine you have a set of 5 letters: A, B, C, D, and E. You want to generate all possible permutations of these letters by selecting  letters. You can use the Permutations API and provide ```'n'``` as 5 and ```'r'``` as 3 and the letter with which you want start calculating the permutations.
    ```python
    my_permutation = perm.find(5,3,'A')
    ```
2. Once the request is made, the API will process the data and return a response in JSON format. The response will include the total number of possible permutations, along with the generated permutations.
    ```json
    {"eventId": "FB1010000000000000000000003004", 
    "n": 5, 
    "r": 3, 
    "numberOfPermutations": 60, 
    "permutationsVariables": ["A"], 
    "inserted_id": "648963a70d4d6ccff1a7b4a0"}
    ```
3. You will now need to select one permuation from the generated permutations and call the API again by providing the next letter that you want to include in the permutation.
4. Repeat the steps until the 3 letters are selected and permutation for 3 letters is generated.