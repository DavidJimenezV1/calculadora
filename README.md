import React, { useState } from 'react';

const Calculator = () => {
const [input, setInput] = useState('');

const handleClick = (value) => {
setInput(input + value);
};

const handleClear = () => {
setInput('');
};

const handleCalculate = () => {
try {
setInput(eval(input).toString());
} catch (error) {
setInput('Error');
}
};

return (
<div style={{ width: '300px', margin: '100px auto', padding: '20px', border: '1px solid #ccc', borderRadius: '10px', textAlign: 'center' }}>
<input
type="text"
value={input}
readOnly
style={{ width: '100%', height: '40px', textAlign: 'right', fontSize: '20px', padding: '10px' }}
/>
<div style={{ marginTop: '20px' }}>
<button onClick={() => handleClick('1')}>1</button>
<button onClick={() => handleClick('2')}>2</button>
<button onClick={() => handleClick('3')}>3</button>
<button onClick={() => handleClick('+')}>+</button>
</div>
<div>
<button onClick={() => handleClick('4')}>4</button>
<button onClick={() => handleClick('5')}>5</button>
<button onClick={() => handleClick('6')}>6</button>
<button onClick={() => handleClick('-')}>-</button>
</div>
<div>
<button onClick={() => handleClick('7')}>7</button>
<button onClick={() => handleClick('8')}>8</button>
<button onClick={() => handleClick('9')}>9</button>
<button onClick={() => handleClick('_')}>_</button>
</div>
<div>
<button onClick={() => handleClick('0')}>0</button>
<button onClick={() => handleClick('.')}>.</button>
<button onClick={handleCalculate}>=</button>
<button onClick={() => handleClick('/')}>/</button>
</div>
<div>
<button onClick={handleClear}>C</button>
</div>
</div>
);
};

export default Calculator;
