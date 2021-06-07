# Understanding Questions:
1. What are the steps of execution from the pressing of the 1 button to the rendering of our updated value? List what part of the code excutes for each step.
* The user presses the 1 button.
* onClick fires the handleOneClick function 
    <CalcButton onClick={handleOneClick} value={1}/>

* handleOneClick function fires addOne() action creator
    const handleOneClick = () => {
    dispatch(addOne());
}

* addOne action creator in the actions folder returns the action type ADD_ONE (which is "ADD_ONE")
    export const addOne = () => {
    return({type:ADD_ONE});
}

*  The dispatch function has access to the reducer function which will take the action returned from the previous step and the current state as arguments. Since ADD_ONE is the action then that case will execute and 1 will be added to the current state.total and returned.
    const reducer = (state, action) => {
    switch(action.type) {
        case(ADD_ONE):
            return({
                ...state,
                total: state.total + 1
            });

* Now 1 will display because state.total is 1.
    <TotalDisplay value={state.total}/>


* TotalDisplay shows the total plus 1.
