# useInput
*React hook to simplify input management*

```javascript
@param {*} initialValue - the initial state, unlike with classes, the state doesn’t have to be an object.
@return [value, handleChange, resetValue] Triple of values
@return {Value} The current state
@return {handleChange} a function that updates it // (event) { setValue(event.target.value) }
@return {resetValue} a function that resets it to the initialValue

@example
import useInput from "@marcusfrancis/useinput";

const Example = () => {
  const { dispatch } = useContext(Store);
  const [email, changeEmail, resetEmail] = useInput("");
  const [password, changePassword, resetPassword] = useInput("");

  const handleSubmit = event => {
    event.preventDefault();
    dispatch({
      type: "USER",
      payload: { email, password }
    });
    resetEmail();
    resetPassword();
  };

  return (
    <>
      <form>
        <input
          type="text"
          placeholder="email"
          value={email}
          onChange={changeEmail}
        />
        <input
          type="text"
          placeholder="password"
          value={password}
          onChange={changePassword}
        />
        <button onClick={handleSubmit}> Submit</button>
      </form>
    </>
  );
};
export default Example;
```
