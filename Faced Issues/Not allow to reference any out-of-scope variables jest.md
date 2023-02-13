# Not allow to reference any out-of-scope variables Jest

## Solutions

Add a prefix `mock` to the variable name. E.g, mockHandleGoBack

```
const mockHandleGoBack = jest.fn();
jest.mock('src/hooks/useBaseAppActions', () => {
  useBaseAppActions: () => ({
    handleGoBack: mockHandleGoBack,
  });
});
expect(mockHandleGoBack).toHaveBeenCalled();
```
